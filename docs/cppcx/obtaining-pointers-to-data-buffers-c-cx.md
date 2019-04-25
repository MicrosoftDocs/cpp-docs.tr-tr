---
title: Veri arabelleklerine işaretçileri alma (C++/CX)
ms.date: 11/19/2018
ms.assetid: db4f9370-dd95-4896-b5b8-4b202284f579
ms.openlocfilehash: 46a81fa9e3d278645b654dca3c652653f6c21037
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62162319"
---
# <a name="obtaining-pointers-to-data-buffers-ccx"></a>Veri arabelleklerine işaretçileri alma (C++/CX)

Windows çalışma zamanı [Windows::Storage::Streams::IBuffer](/uwp/api/windows.storage.streams.ibuffer) arabirimi veri arabelleklerinin erişmek için dilden bağımsız, akış tabanlı bir yol sağlar. C++'ta robuffer.h içinde tanımlanan bir Windows çalışma zamanı kitaplığı IBufferByteAccess arabirimini kullanarak bir ham işaretçi temel alınan bayt dizisine elde edebilirsiniz. Bu yaklaşım kullanarak verilerin gereksiz kopyalarını yapmadan bayt dizisi yerinde değiştirebilirsiniz.

Aşağıdaki diyagramda, kaynağı bir XAML görüntü öğesi gösterir bir [Windows::UI::Xaml::Media::Imaging WriteableBitmap](/uwp/api/Windows.UI.Xaml.Media.Imaging.WriteableBitmap). Herhangi bir dilde yazılmış bir istemci uygulaması için başvuru geçirebilirsiniz `WriteableBitmap` C++ için kod ve C++ başvurusu temel alınan arabelleğe almak için kullanabilirsiniz. C++ ile yazılmış bir evrensel Windows platformu uygulamasında paketleyerek bir Windows çalışma zamanı bileşeni olmadan aşağıdaki örnekte kaynak kodda doğrudan işlevi kullanabilirsiniz.

![C&#43; &#43; doğrudan piksel verilere erişen kodu](../cppcx/media/ibufferbyteaccessdiagram.png "C&#43; &#43; doğrudan piksel verilere erişen kodu")

## <a name="getpointertopixeldata"></a>GetPointerToPixelData

Aşağıdaki yöntem kabul eden bir [Windows::Storage::Streams::IBuffer](/uwp/api/windows.storage.streams.ibuffer) ve temel alınan bayt dizisine bir ham işaretçiyi döndürür. İşlev çağrısı için geçirin bir [WriteableBitmap::PixelBuffer](/uwp/api/windows.ui.xaml.media.imaging.writeablebitmap.pixelbuffer) özelliği.

```cpp
#include <wrl.h>
#include <robuffer.h>
using namespace Windows::Storage::Streams;
using namespace Microsoft::WRL;
typedef uint8 byte;
// Retrieves the raw pixel data from the provided IBuffer object.
// Warning: The lifetime of the returned buffer is controlled by
// the lifetime of the buffer object that's passed to this method.
// When the buffer has been released, the pointer becomes invalid
// and must not be used.
byte* Class1::GetPointerToPixelData(IBuffer^ pixelBuffer, unsigned int *length)
{
    if (length != nullptr)
    {
        *length = pixelBuffer ->Length;
    }
    // Query the IBufferByteAccess interface.
    ComPtr<IBufferByteAccess> bufferByteAccess;
    reinterpret_cast<IInspectable*>( pixelBuffer)->QueryInterface(IID_PPV_ARGS(&bufferByteAccess));

    // Retrieve the buffer data.
    byte* pixels = nullptr;
    bufferByteAccess->Buffer(&pixels);
    return pixels;
}
```

## <a name="complete-example"></a>Tam Örnek

Aşağıdaki adımlar gönderen bir C# Evrensel Windows platformu uygulaması oluşturma işlemini gösterir bir `WriteableBitmap` bir C++ Windows çalışma zamanı bileşeni DLL için. C++ kodu piksel arabelleği için bir işaretçi alır ve basit bir yerinde değişiklikle görüntüye gerçekleştirir. Alternatif olarak, Visual Basic veya JavaScript yerine C#, C++, istemci uygulama oluşturabilirsiniz. C++ kullanırsanız, DLL bileşeni gerekmez; Bu yöntemleri doğrudan MainPage sınıfının veya belirlediğiniz başka bir sınıfın yalnızca ekleyebilirsiniz.

#### <a name="create-the-client"></a>İstemcisi oluşturma

1. Bir C# Evrensel Windows platformu uygulaması oluşturmak için boş uygulaması proje şablonunu kullanın.

1. MainPage.xaml içinde

   - Değiştirmek için bu XAML kullanmak `Grid` öğesi:

        ```xml
        <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <StackPanel HorizontalAlignment="Left" Margin="176,110,0,0" VerticalAlignment="Top" Width="932">
                <Image x:Name="Pic"/>
                <Button Content="Process Image" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Height="47" Click="Button_Click_1"/>
            </StackPanel>
        </Grid>
        ```

1. In MainPage.xaml.cs

   1. Bu ad alanı bildirimi ekleyin:

        ```csharp
        using Windows.Storage;
        using Windows.Storage.FileProperties;
        using Windows.UI.Xaml.Media.Imaging;
        using Windows.Storage.Streams;
        using Windows.Storage.Pickers;
        ```

   1. Ekleme bir `WriteableBitmap` üye değişkeni `MainPage` sınıfı ve adlandırın `m_bm`.

        ```csharp
        private WriteableBitmap m_bm;
        ```

   1. Değiştirmek için aşağıdaki kodu kullanın `OnNavigatedTo` metot taslağı. Uygulama başlatıldığında bu dosya Seçici açılır. (Dikkat `async` anahtar sözcüğü için işlev imzasına eklenir).

        ```csharp
        async protected override void OnNavigatedTo(NavigationEventArgs e)
        {
            FileOpenPicker openPicker = new FileOpenPicker();
            openPicker.ViewMode = PickerViewMode.Thumbnail;
            openPicker.SuggestedStartLocation = PickerLocationId.PicturesLibrary;
            openPicker.FileTypeFilter.Add(".jpg");
            openPicker.FileTypeFilter.Add(".jpeg");
            openPicker.FileTypeFilter.Add(".png");

            StorageFile file = await openPicker.PickSingleFileAsync();
            if (file != null)
            {
                // Get the size of the image for the WriteableBitmap constructor.
                ImageProperties props = await file.Properties.GetImagePropertiesAsync();
                m_bm = new WriteableBitmap((int)props.Height, (int)props.Width);
                m_bm.SetSource(await file.OpenReadAsync());
                Pic.Source = m_bm;
            }
            else
            {
                //  Handle error...
            }
        }
        ```

   1. Düğmesine tıklayarak olay işleyicisi ekleyin. (Çünkü `ImageManipCPP` ad alanı başvurusu taşınmadığından oluşturuldu ancak düzenleyici penceresinde dalgalı çizgi olabilir.)

        ```csharp
        async private void Button_Click_1(object sender, RoutedEventArgs e)
        {
            ImageManipCPP.Class1 obj = new ImageManipCPP.Class1();
            await obj.Negativize(m_bm);
            Pic.Source = m_bm;
        }
        ```

#### <a name="create-the-c-component"></a>C++ bileşeni oluşturma

1. Daha sonra mevcut çözüme yeni bir C++ Windows çalışma zamanı bileşeni ekleyin ve adlandırın `ImageManipCPP`. Bu projeye sağ tıklayarak ve C# projesinde buna bir başvuru ekleyin **Çözüm Gezgini** seçip **Ekle**, **başvuru**.

1. İçinde Class1.h

   1. Bu ekleme `typedef` ikinci satırında, yalnızca sonra `#pragma once`:

        ```cpp
        typedef uint8 byte;
        ```

   1. Ekleme `WebHostHidden` öznitelik başına kısalarak `Class1` bildirimi.

        ```cpp
        [Windows::Foundation::Metadata::WebHostHidden]
        ```

   1. Bu genel yöntem imzası için ekleme `Class1`:

        ```cpp
        Windows::Foundation::IAsyncAction^ Negativize(Windows::UI::Xaml::Media::Imaging::WriteableBitmap^ bm);
        ```

   1. İmzasının ekleme `GetPointerToPixelData` önceki kod parçacığında gösterilen yöntemi. Bu yöntem özel olduğundan emin olun.

1. İçinde Class1.cpp

   1. Bu ekleme `#include` yönergeleri ve ad alanı bildirimi:

        ```cpp
        #include <ppltasks.h>
        #include <wrl.h>
        #include <robuffer.h>

        using namespace Windows::Storage;
        using namespace Windows::UI::Xaml::Media::Imaging;
        using namespace Windows::Storage::Streams;
        using namespace Microsoft::WRL;
        ```

   1. Uygulamasını ekleme `GetPointerToPixelData` önceki kod parçacığında.

   1. Uygulamasını ekleme `Negativize`. Bu yöntem, her pikselin RGB değeri değerini tersine çevirerek negatif bir film benzer bir efekti oluşturur. Biz, yöntemi zaman uyumsuz olun, çünkü daha büyük görüntülerinde tamamlanması algılanabilir bir süre alabilir.

        ```cpp
        IAsyncAction^ Class1::Negativize(WriteableBitmap^ bm)
        {
            unsigned int length;
            byte* sourcePixels = GetPointerToPixelData(bm->PixelBuffer, &length);
            const unsigned int width = bm->PixelWidth;
            const unsigned int height = bm->PixelHeight;

            return create_async([this, width, height, sourcePixels]
            {
                byte* temp = sourcePixels;
                for(unsigned int k = 0; k < height; k++)
                {
                    for (unsigned int i = 0; i < (width * 4); i += 4)
                    {
                        int pos = k * (width * 4) + (i);
                        temp[pos] = ~temp[pos];
                        temp[pos + 1] = ~temp[pos + 1] / 3;
                        temp[pos + 2] = ~temp[pos + 2] / 2;
                        temp[pos + 3] = ~temp[pos + 3];
                    }
                }
            });

        }
        ```

      > [!NOTE]
      > İşlemi paralel hale getirmek için AMP veya paralel desenler kitaplığı kullanıyorsanız bu yöntem daha hızlı çalışabilir.

1. En az bir resim resimler klasörünüzde olması ve derlemek ve programı çalıştırmak için F5 tuşuna basarak emin olun.
