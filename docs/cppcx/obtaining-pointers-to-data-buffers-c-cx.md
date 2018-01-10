---
title: "Veri arabelleklerinin işaretçiler edinme (C + +/ CX) | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db4f9370-dd95-4896-b5b8-4b202284f579
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c914241682aa53735d27138da2864b0db124c8d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="obtaining-pointers-to-data-buffers-ccx"></a>Veri arabelleklerinin işaretçiler edinme (C + +/ CX)
Windows çalışma zamanı içinde [Windows::Storage::Streams::IBuffer](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.ibuffer.aspx) arabirim veri arabelleklerinin erişmek için dilden, akış tabanlı bir yol sağlar. C++'ta robuffer.h içinde tanımlanan Windows çalışma zamanı kitaplığı IBufferByteAccess arabirimini kullanarak temel alınan bayt dizisi ham işaretçi alabilirsiniz. Bu yaklaşımı kullanarak verileri gereksiz tüm kopyalarını yapmadan bayt dizisi yerinde değiştirebilirsiniz.  
  
 Aşağıdaki diyagramda, kaynağı bir XAML bir görüntü öğesi gösteren bir [Windows::UI::Xaml::Media::Imaging WriteableBitmap](http://msdn.microsoft.com/%20library/windows/apps/windows.ui.xaml.media.imaging.writeablebitmap.aspx). Herhangi bir dilde yazılmış bir istemci uygulaması için bir başvuru geçirebilirsiniz `WriteableBitmap` C++ için kod ve C++ başvuru alttaki arabelleğe almak için kullanabilirsiniz. C++ ile yazılmış bir evrensel Windows platformu uygulamasında, bir Windows çalışma zamanı bileşeni paketleme olmadan aşağıdaki örnekte kaynak kodunda doğrudan işlevi kullanabilirsiniz.  
  
 ![C# 43; &#43; piksel verilerini doğrudan erişim kodu](../cppcx/media/ibufferbyteaccessdiagram.png "IBufferByteAccessDiagram")  
  
## <a name="getpointertopixeldata"></a>GetPointerToPixelData  
 Aşağıdaki yöntem kabul eden bir [Windows::Storage::Streams::IBuffer](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.ibuffer.aspx) ve raw işaretçi temel alınan bayt dizisi döndürür. Bir işlevi çağırmak için geçirin bir [WriteableBitmap::PixelBuffer](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.media.imaging.writeablebitmap.pixelbuffer.aspx) özelliği.  
  
```  
  
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
 Aşağıdaki adımlar başarılı bir C# Evrensel Windows platformu uygulamasının nasıl oluşturulacağını gösterir bir `WriteableBitmap` C++ Windows çalışma zamanı bileşeni DLL için. C++ kodu piksel arabellek için bir işaretçi alır ve basit bir yerinde değişiklikle görüntüde gerçekleştirir. Alternatif olarak, Visual Basic, JavaScript ya da C++ yerine C# içinde istemci uygulaması oluşturabilirsiniz. C++ kullanırsanız, DLL bileşen gerekmez; Bu yöntemler yalnızca, doğrudan MainPage sınıfı veya tanımladığınız başka bir sınıf da ekleyebilirsiniz.  
  
#### <a name="create-the-client"></a>İstemci oluşturma  
  
1.  Bir C# Evrensel Windows Platform uygulaması oluşturmak için boş uygulaması proje şablonunu kullanın.  
  
2.  İçinde MainPage.xaml  
  
    -   Değiştirmek için bu XAML kullanmak `Grid` öğe:  
  
        ```cpp  
        <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">  
                <StackPanel HorizontalAlignment="Left" Margin="176,110,0,0" VerticalAlignment="Top" Width="932">  
                    <Image x:Name="Pic"/>  
                    <Button Content="Process Image" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Height="47" Click="Button_Click_1"/>  
                </StackPanel>  
            </Grid>  
        ```  
  
3.  MainPage.xaml.cs dosyasında  
  
    1.  Bu ad alanı bildirimleri ekleyin:  
  
        ```  
        using Windows.Storage;  
        using Windows.Storage.FileProperties;  
        using Windows.UI.Xaml.Media.Imaging;  
        using Windows.Storage.Streams;  
        using Windows.Storage.Pickers;  
        ```  
  
    2.  Ekleme bir `WriteableBitmap` üye değişkeni `MainPage` sınıfı ve adlandırın `m_bm`.  
  
        ```  
        private WriteableBitmap m_bm;  
        ```  
  
    3.  Değiştirmek için aşağıdaki kodu kullanın `OnNavigatedTo` yöntemi saplama. Uygulama başlatıldığında bu dosya seçiciyi açar. (Dikkat `async` anahtar sözcüğü için işlev imzasına eklenir).  
  
        ```c#  
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
  
    4.  Düğme tıklaması için olay işleyicisini ekleyin. (Çünkü `ImageManipCPP` ad alanı başvurusunu kurmadı oluşturulmuş henüz Düzenleyicisi penceresinde dalgalı alt çizgiyle sahip olabilirsiniz.)  
  
        ```  
        async private void Button_Click_1(object sender, RoutedEventArgs e)  
                {  
                    ImageManipCPP.Class1 obj = new ImageManipCPP.Class1();  
                    await obj.Negativize(m_bm);  
                    Pic.Source = m_bm;  
                }  
        ```  
  
#### <a name="create-the-c-component"></a>C++ bileşeni oluşturma  
  
1.  Yeni bir C++ Windows çalışma zamanı bileşeni varolan çözüme ekleyin ve adını `ImageManipCPP`. Bu proje üzerinde sağ tıklayarak C# projesinde bir başvuru ekleyin **Çözüm Gezgini** ve seçme **Ekle**, **başvuru**.  
  
2.  İçinde Class1.h  
  
    1.  Bu ekleme `typedef` ikinci satırında, yalnızca sonra `#pragma once`:  
  
        ```  
        typedef uint8 byte;  
  
        ```  
  
    2.  Ekleme `WebHostHidden` öznitelik başına yalnızca yukarıda `Class1` bildirimi.  
  
        ```  
        [Windows::Foundation::Metadata::WebHostHidden]  
        ```  
  
    3.  Bu genel yöntem imza ekleme `Class1`:  
  
        ```  
        Windows::Foundation::IAsyncAction^ Negativize(Windows::UI::Xaml::Media::Imaging::WriteableBitmap^ bm);  
        ```  
  
    4.  İmzadan eklemek `GetPointerToPixelData` önceki kod parçacığında gösterildiği yöntemi. Bu yöntemi özel olduğundan emin olun.  
  
3.  İçinde Class1.cpp  
  
    1.  Bunlar ekleme `#include` yönergeleri ve ad alanı bildirimi:  
  
        ```  
  
        #include <ppltasks.h>  
        #include <wrl.h>  
        #include <robuffer.h>  
  
        using namespace Windows::Storage;  
        using namespace Windows::UI::Xaml::Media::Imaging;  
        using namespace Windows::Storage::Streams;  
        using namespace Microsoft::WRL;  
  
        ```  
  
    2.  Uygulamasını eklemek `GetPointerToPixelData` önceki kod parçacığını gelen.  
  
    3.  Uygulamasını eklemek `Negativize`. Bu yöntem her RGB değeri piksel olarak döndürerek negatif bir film benzer bir efekt oluşturur. Biz, yöntemi zaman uyumsuz olun, çünkü büyük görüntülerinde algılanabilir tutar tamamlanması uzun zaman alabilir.  
  
        ```  
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
        >  İşlemi paralel hale AMP veya paralel Desen kitaplığı kullanıyorsanız bu yöntem daha hızlı çalışabilir.  
  
4.  En az bir resim resimler klasörünüzde olması ve derlemek ve programı çalıştırmak için F5 tuşuna basarak emin olun.