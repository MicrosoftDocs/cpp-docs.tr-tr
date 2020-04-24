---
title: Veri Arabelleklerine İşaretçileri Alma (C++/CX)
ms.date: 11/19/2018
ms.assetid: db4f9370-dd95-4896-b5b8-4b202284f579
ms.openlocfilehash: 9e60adc4163e96349f6f4bafa919944e5d8d5b51
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032375"
---
# <a name="obtaining-pointers-to-data-buffers-ccx"></a>Veri Arabelleklerine İşaretçileri Alma (C++/CX)

Windows Runtime'da [Windows:Storage::Streams::IBuffer](/uwp/api/windows.storage.streams.ibuffer) arabirimi, veri arabelleklerine erişmek için dilden bağımsız, akış tabanlı bir araç sağlar. C++'da, robuffer.h'de tanımlanan Windows Runtime Library IBufferByteAccess arabirimini kullanarak altta yatan bayt dizisini ham bir işaretçi elde edebilirsiniz. Bu yaklaşımı kullanarak, verilerin gereksiz kopyalarını yapmadan bayt dizisini yerinde değiştirebilirsiniz.

Aşağıdaki diyagram, kaynağı Windows olan bir XAML görüntü öğesini [gösterir::UI::Xaml::Medya::Görüntüleme YazılabilirBitmap](/uwp/api/windows.ui.xaml.media.imaging.writeablebitmap). Herhangi bir dilde yazılmış bir istemci uygulaması C++ `WriteableBitmap` koduna bir başvuru geçirebilir ve ardından C++ temel arabellekte almak için başvuruyu kullanabilir. C++'da yazılmış evrensel bir Windows Platformu uygulamasında, aşağıdaki örnekteki işlevi doğrudan kaynak kodda, windows runtime bileşeninde paketlemeden kullanabilirsiniz.

![Piksel verilerine doğrudan erişen C&#43;&#43; kodu](../cppcx/media/ibufferbyteaccessdiagram.png "Piksel verilerine doğrudan erişen C&#43;&#43; kodu")

## <a name="getpointertopixeldata"></a>GetpointertopixelData

Aşağıdaki yöntem bir [Windows kabul eder::Depolama::Akışlar::IAraffer](/uwp/api/windows.storage.streams.ibuffer) ve altta yatan bayt dizisine ham işaretçi döndürür. İşlevi çağırmak için [WriteableBitmap::PixelBuffer](/uwp/api/windows.ui.xaml.media.imaging.writeablebitmap.pixelbuffer) özelliğini geçirin.

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

Aşağıdaki adımlar, C++ Windows Runtime bileşeni DLL'ye geçen `WriteableBitmap` bir C# Evrensel Windows Platformu uygulamasının nasıl oluşturulacağını gösterir. C++ kodu piksel arabelleği için bir işaretçi alır ve görüntü üzerinde basit bir yerinde değişiklik gerçekleştirir. Alternatif olarak, c# yerine Visual Basic, JavaScript veya C++ istemci uygulamasını oluşturabilirsiniz. C++'ı kullanıyorsanız, DLL bileşenine ihtiyacınız yoktur; bu yöntemleri doğrudan MainPage sınıfına veya tanımladığınız başka bir sınıfa ekleyebilirsiniz.

#### <a name="create-the-client"></a>İstemci oluşturma

1. C# Evrensel Windows Platformu uygulaması oluşturmak için Boş uygulama proje şablonuna kullanın.

1. Ana Sayfa.xaml içinde

   - Öğeyi değiştirmek için bu `Grid` XAML'yi kullanın:

        ```xml
        <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <StackPanel HorizontalAlignment="Left" Margin="176,110,0,0" VerticalAlignment="Top" Width="932">
                <Image x:Name="Pic"/>
                <Button Content="Process Image" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Height="47" Click="Button_Click_1"/>
            </StackPanel>
        </Grid>
        ```

1. MainPage.xaml.cs yılında

   1. Şu ad alanı bildirimleri ekleyin:

        ```csharp
        using Windows.Storage;
        using Windows.Storage.FileProperties;
        using Windows.UI.Xaml.Media.Imaging;
        using Windows.Storage.Streams;
        using Windows.Storage.Pickers;
        ```

   1. Sınıfa `WriteableBitmap` bir üye değişken ekleyin ve adını. `m_bm` `MainPage`

        ```csharp
        private WriteableBitmap m_bm;
        ```

   1. Yöntem saplaması yerine `OnNavigatedTo` aşağıdaki kodu kullanın. Bu, uygulama başlatıldığında dosya seçiciyi açar. (Anahtar kelimenin işlev imzasına `async` eklenmiştir) dikkat edin).

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

   1. Düğme tıklaması için olay işleyicisini ekleyin. (Ad `ImageManipCPP` alanı başvurusu henüz oluşturulmadığından, düzenleyici penceresinde dalgalı bir alt çizgi olabilir.)

        ```csharp
        async private void Button_Click_1(object sender, RoutedEventArgs e)
        {
            ImageManipCPP.Class1 obj = new ImageManipCPP.Class1();
            await obj.Negativize(m_bm);
            Pic.Source = m_bm;
        }
        ```

#### <a name="create-the-c-component"></a>C++ bileşenini oluşturma

1. Varolan çözüme yeni bir C++ Windows Runtime `ImageManipCPP`bileşeni ekleyin ve adlandırın. **Çözüm Gezgini'ndeki** projeye sağ tıklayarak ve **Ekle**, **Başvuru**' yu seçerek C# projesinde projeye bir referans ekleyin.

1. Sınıf1.h olarak

   1. Bunu `typedef` ikinci satıra ekleyin, `#pragma once`hemen sonra:

        ```cpp
        typedef uint8 byte;
        ```

   1. `WebHostHidden` Özniteliği `Class1` bildirimin başlangıcının hemen üzerine ekleyin.

        ```cpp
        [Windows::Foundation::Metadata::WebHostHidden]
        ```

   1. Bu ortak yöntem `Class1`imzasını ekleyin:

        ```cpp
        Windows::Foundation::IAsyncAction^ Negativize(Windows::UI::Xaml::Media::Imaging::WriteableBitmap^ bm);
        ```

   1. Önceki kod snippet gösterilen `GetPointerToPixelData` yöntemden imza ekleyin. Bu yöntemin özel olduğundan emin olun.

1. Sınıf1.cpp olarak

   1. Bu `#include` yönergeleri ve ad alanı bildirimlerini ekleyin:

        ```cpp
        #include <ppltasks.h>
        #include <wrl.h>
        #include <robuffer.h>

        using namespace Windows::Storage;
        using namespace Windows::UI::Xaml::Media::Imaging;
        using namespace Windows::Storage::Streams;
        using namespace Microsoft::WRL;
        ```

   1. Önceki kod `GetPointerToPixelData` parçacığının uygulamasını ekleyin.

   1. Uygulamasını `Negativize`ekleyin. Bu yöntem, pikseldeki her RGB değerinin değerini tersine çevirerek film negatifine benzeyen bir efekt oluşturur. Yöntemi eşzamanlı yapıyoruz çünkü daha büyük görüntülerde tamamlanması algılanabilir bir miktar zaman alabilir.

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
      > İşlemi paralelleştirmek için AMP veya Paralel Desenler Kitaplığı kullanırsanız, bu yöntem daha hızlı çalışabilir.

1. Resimler klasörünüzde en az bir resim olduğundan emin olun ve ardından programı derlemek ve çalıştırmak için F5 tuşuna basın.
