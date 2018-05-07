---
title: CLR tümleştirme (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 50b455bd3b6fd4a96c3181b60904cb7a3250e866
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="clr-integration-ccx"></a>CLR tümleştirme (C + +/ CX)
Bazı Windows çalışma zamanı türleri özel işleme C + alma +/ CX ve (CLR) ortak dil çalışma zamanı tabanlı diller. Bu makalede, başka bir dil için bir dil nasıl birkaç türü harita anlatılmaktadır. Örneğin, CLR Windows.Foundation.IVector eşlendiğini System.Collections.IList, Windows.Foundation.IMap System.Collections.IDictionary ve benzeri. Benzer şekilde, C + +/ CX özel türleri Platform::Delegate ve Platform::String gibi eşler.  
  
## <a name="mapping-the-windows-runtime-to-ccx"></a>Windows çalışma zamanı eşleme C + +/ CX  
 C + zaman +/ CX Windows (.winmd) meta veri dosyasını okur, derleyici otomatik olarak ortak Windows çalışma zamanı ad alanları ve türler C + eşler +/ CX ad alanları ve türler. Örneğin, sayısal Windows çalışma zamanı tür `UInt32` otomatik olarak eşlenmiş `default::uint32`.  
  
 C + +/ CX eşlemeleri diğer çeşitli Windows çalışma zamanı türlerine **Platform** ad alanı. Örneğin, **Windows::Foundation** salt okunur bir Unicode metin dizesini temsil eder, HSTRING tanıtıcı eşlendiği C + +/ CX `Platform::String` sınıfı. Windows çalışma zamanı işlemi HRESULT hata döndürdüğünde, onu bir C + eşlenmiş +/ CX `Platform::Exception`. Daha fazla bilgi için bkz: [yerleşik türleri](http://msdn.microsoft.com/en-us/acc196fd-09da-4882-b554-6c94685ec75f).  
  
 C + +/ CX türü işlevselliğini geliştirmek için Windows çalışma zamanı ad alanlarında belirli türleri de eşler. Bu tür, C + +/ CX Yardımcısı oluşturucular ve C++ için özeldir ve tür standart .winmd dosyasında kullanılabilir değil yöntemleri sağlar.  
  
 Aşağıdaki listeler, yeni oluşturucular ve yardımcı yöntemler desteği değeri yapılar gösterir. Yapı başlatma listeleri kullanan kodu daha önceden yazılmış varsa, yeni eklenen oluşturucular kullanacak şekilde değiştirin.  
  
 **Windows::Foundation**  
  
-   noktası  
  
-   Rect  
  
-   Boyut  
  
 **Windows::UI**  
  
-   Renk  
  
 **Windows::UI::Xaml**  
  
-   CornerRadius  
  
-   Süre  
  
-   GridLength  
  
-   Kalınlığı  
  
 **Windows::UI::Xaml::Interop**  
  
1.  TypeName  
  
 **Windows::UI::Xaml::Media**  
  
-   Matris  
  
 **Windows::UI::Xaml::Media::Animation**  
  
-   KeyTime  
  
-   RepeatBehavior  
  
 **Windows::UI::Xaml::Media::Media3D**  
  
-   Matrix3D  
  
## <a name="mapping-the-clr-to-ccx"></a>CLR eşleme C + +/ CX  
 Visual C++ veya C# Derleyicileri .winmd dosyasını okumak, bunlar otomatik olarak belirli türleri meta veri dosyasında uygun C + eşleyin +/ CX veya CLR türü. Örneğin, CLR IVector içinde\<T > arabirimini IList için eşlenen\<T >. Ancak C + +/ CX, IVector\<T > başka bir türüne arabirimi eşlenen değil.  
  
 IReference\<T > Windows çalışma zamanı'nda eşler için null atanabilir\<T > .NET içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Diğer dilleri ile birlikte çalışma](../cppcx/interoperating-with-other-languages-c-cx.md)