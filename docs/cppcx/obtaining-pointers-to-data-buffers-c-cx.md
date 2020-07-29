---
title: Veri Arabelleklerine İşaretçileri Alma (C++/CX)
ms.date: 11/19/2018
ms.assetid: db4f9370-dd95-4896-b5b8-4b202284f579
ms.openlocfilehash: 0b5163dd111adfe5c745a1ad3bbcdc06a675c52c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87185547"
---
# <a name="obtaining-pointers-to-data-buffers-ccx"></a>Veri Arabelleklerine İşaretçileri Alma (C++/CX)

Windows Çalışma Zamanı [Windows:: Storage:: Streams:: IBuffer](/uwp/api/windows.storage.streams.ibuffer) arabirimi, veri arabelleklerine erişmek için dilden bağımsız, akış tabanlı bir yol sağlar. C++ ' da, robuffer. h içinde tanımlanan Windows Çalışma Zamanı Kitaplığı ıbufferbyteaccess arabirimini kullanarak, temel alınan bayt dizisine ham bir işaretçi alabilirsiniz. Bu yaklaşımı kullanarak, verilerin gereksiz kopyalarını oluşturmadan, bayt dizisini yerinde değiştirebilirsiniz.

Aşağıdaki diyagramda, kaynağı bir [Windows:: UI:: XAML:: Media:: Imaging WriteableBitmap](/uwp/api/windows.ui.xaml.media.imaging.writeablebitmap)olan bir xaml Image öğesi gösterilmektedir. Herhangi bir dilde yazılmış bir istemci uygulaması, C++ koduna bir başvuru geçirebilir `WriteableBitmap` ve c++ bu başvuruyu temel alınan arabelleğe almak için kullanabilir. C++ dilinde yazılmış Evrensel Windows Platformu bir uygulamada, aşağıdaki örnekteki işlevi, bir Windows Çalışma Zamanı bileşeninde paketlemeden doğrudan kaynak kodunda kullanabilirsiniz.

![&#43;&#43; doğrudan piksel verilerine erişen kod](../cppcx/media/ibufferbyteaccessdiagram.png "&#43;&#43; doğrudan piksel verilerine erişen kod")

## <a name="getpointertopixeldata"></a>GetPointerToPixelData

Aşağıdaki yöntem bir [Windows:: Storage:: Streams:: IBuffer](/uwp/api/windows.storage.streams.ibuffer) kabul eder ve temel alınan bayt dizisine ham bir işaretçi döndürür. İşlevi çağırmak için bir [WriteableBitmap::P ixelbuffer](/uwp/api/windows.ui.xaml.media.imaging.writeablebitmap.pixelbuffer) özelliğini geçirin.

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

Aşağıdaki adımlarda, bir `WriteableBitmap` C++ Windows çalışma zamanı BILEŞEN dll 'sine ileten C# Evrensel Windows Platformu uygulamasının nasıl oluşturulacağı gösterilmektedir. C++ kodu, piksel arabelleğine yönelik bir işaretçi alır ve görüntüde basit bir yerinde değişiklik gerçekleştirir. Alternatif olarak, istemci uygulamasını C# yerine Visual Basic, JavaScript veya C++ ' da oluşturabilirsiniz. C++ kullanıyorsanız, bileşen DLL 'SI gerekmez; yalnızca bu yöntemleri doğrudan MainPage sınıfına veya tanımladığınız başka bir sınıfa ekleyebilirsiniz.

#### <a name="create-the-client"></a>İstemci oluşturma

1. Bir C# Evrensel Windows platformu uygulaması oluşturmak için boş uygulama proje şablonunu kullanın.

1. MainPage. xaml içinde

   - Öğeyi değiştirmek için bu XAML 'yi kullanın `Grid` :

        ```xml
        <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <StackPanel HorizontalAlignment="Left" Margin="176,110,0,0" VerticalAlignment="Top" Width="932">
                <Image x:Name="Pic"/>
                <Button Content="Process Image" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Height="47" Click="Button_Click_1"/>
            </StackPanel>
        </Grid>
        ```

1. MainPage.xaml.cs içinde

   1. Şu ad alanı bildirimlerini ekleyin:

        ```csharp
        using Windows.Storage;
        using Windows.Storage.FileProperties;
        using Windows.UI.Xaml.Media.Imaging;
        using Windows.Storage.Streams;
        using Windows.Storage.Pickers;
        ```

   1. Sınıfa bir `WriteableBitmap` üye değişkeni ekleyin `MainPage` ve bunu adlandırın `m_bm` .

        ```csharp
        private WriteableBitmap m_bm;
        ```

   1. Yöntem saplamasını değiştirmek için aşağıdaki kodu kullanın `OnNavigatedTo` . Bu, uygulama başlatıldığında dosya seçiciyi açar. ( `async` Anahtar sözcüğünün işlev imzasına eklendiğini unutmayın).

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

   1. Düğme tıklayı için olay işleyicisini ekleyin. ( `ImageManipCPP` Ad alanı başvurusu henüz oluşturulmadığından, düzenleyici penceresinde dalgalı alt çizgiye sahip olabilir.)

        ```csharp
        async private void Button_Click_1(object sender, RoutedEventArgs e)
        {
            ImageManipCPP.Class1 obj = new ImageManipCPP.Class1();
            await obj.Negativize(m_bm);
            Pic.Source = m_bm;
        }
        ```

#### <a name="create-the-c-component"></a>C++ bileşeni oluşturma

1. Mevcut çözüme yeni bir C++ Windows Çalışma Zamanı bileşeni ekleyin ve bunu adlandırın `ImageManipCPP` . **Çözüm Gezgini** ' de projeye sağ tıklayıp **Ekle**, **başvuru**' yı seçerek C# projesinde buna bir başvuru ekleyin.

1. Class1. h içinde

   1. Bunu **`typedef`** ikinci satıra, hemen sonra ekleyin `#pragma once` :

        ```cpp
        typedef uint8 byte;
        ```

   1. `WebHostHidden`Özniteliği bildirimin başlangıcına hemen yukarıya ekleyin `Class1` .

        ```cpp
        [Windows::Foundation::Metadata::WebHostHidden]
        ```

   1. Bu ortak yöntem imzasını şu şekilde ekleyin `Class1` :

        ```cpp
        Windows::Foundation::IAsyncAction^ Negativize(Windows::UI::Xaml::Media::Imaging::WriteableBitmap^ bm);
        ```

   1. `GetPointerToPixelData`Önceki kod parçacığında gösterilen yöntemden imzayı ekleyin. Bu yöntemin özel olduğundan emin olun.

1. Class1. cpp içinde

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

   1. `GetPointerToPixelData`Önceki kod parçacığındaki uygulamasını ekleyin.

   1. Uygulamasını ekleyin `Negativize` . Bu yöntem, pikselin her bir RGB değerinin değerini ters çevirerek film negatifine benzeyen bir efekt oluşturur. Daha büyük görüntülerde algılanabilir bir süre sürebileceğinden, yöntemi zaman uyumsuz hale sunuyoruz.

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
      > Bu yöntem, işlemi paralel hale getirmek için AMP veya paralel Desenler kitaplığı kullanırsanız daha hızlı çalışabilir.

1. Resimler klasörünüzde en az bir resme sahip olduğunuzdan emin olun ve ardından programı derlemek ve çalıştırmak için F5 tuşuna basın.
