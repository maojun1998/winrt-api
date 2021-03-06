---
-api-id: M:Windows.UI.Input.Inking.InkManager.LoadAsync(Windows.Storage.Streams.IInputStream)
-api-type: winrt method
-api-device-family-note: xbox
---

<!-- Method syntax
public Windows.Foundation.IAsyncActionWithProgress<ulong> LoadAsync(Windows.Storage.Streams.IInputStream inputStream)
-->

# Windows.UI.Input.Inking.InkManager.LoadAsync

## -description
> [!NOTE]
> For Universal Windows app using Extensible Application Markup Language (XAML), we recommend using [InkPresenter](inkpresenter.md) and the [InkCanvas](../windows.ui.xaml.controls/inkcanvas.md) control instead of [InkManager](inkmanager.md).

Asynchronously loads all [InkStroke](inkstroke.md) objects from the specified stream to the [InkStroke](inkstroke.md) collection that is managed by the [InkManager](inkmanager.md).

Ink data is serialized as Ink Serialized Format (ISF) metadata and embedded into a Graphics Interchange Format (GIF) file.

## -parameters
### -param inputStream
The stream that contains the stroke collection. An [IRandomAccessStream](../windows.storage.streams/irandomaccessstream.md) (requires [IOutputStream](../windows.storage.streams/ioutputstream.md)) object can be specified instead.

## -returns
The status of the asynchronous operation as the number of bytes fetched. For more information, see [ReadAsync](http://msdn.microsoft.com/library/4d5046c8-a1d2-435f-9c3d-64c242fc20cf) method.

## -remarks
Embedding the metadata into a Graphics Interchange Format (GIF) file enables ink to be viewed in applications that are not ink-enabled while maintaining full fidelity for ink-enabled applications. This format is ideal for transporting ink content within an HTML file and making it usable by both ink and non-ink applications. 

> [!NOTE]
> Ink Serialized Format (ISF) is the most compact persistent representation of ink. It can be embedded within a binary document format or placed directly on the Clipboard while preserving various ink properties such as pressure, width, color, tilt, twist, and so on.

## -examples
The `loadStrokes` function in this example demonstrates how to:
+ Display a file open screen where the file type is constrained to Graphics Interchange Format (GIF) format using the [FileOpenPicker](../windows.storage.pickers/fileopenpicker.md) object.
+ Set up an input stream through the [OpenAsync](../windows.storage/storagefile_openasync.md) method.
+ Use the [LoadAsync](inkmanager_loadasync.md) method of an [InkManager](inkmanager.md) object (`inkManager`) to de-serialize the ink data from a Graphics Interchange Format (GIF) file (`storageFile`).




[!code-js[LoadStrokes](../windows.ui.input.inking/code/CaptureInkData_JS/js/InkPage.js#SnippetLoadStrokes)]

## -see-also
[Pen and stylus interactions](http://msdn.microsoft.com/library/3da4f2d2-5405-42a1-9ed9-3a87bcd84c43), [Ink sample](http://go.microsoft.com/fwlink/p/?LinkID=620308), [Simple ink sample](http://go.microsoft.com/fwlink/p/?LinkID=620312), [Complex ink sample](http://go.microsoft.com/fwlink/p/?LinkID=620314)
