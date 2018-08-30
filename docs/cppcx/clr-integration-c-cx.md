---
title: CLR tümleştirme (C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0c2acf17831e5cb3a2e0118ffe3606bc7beef25
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212994"
---
# <a name="clr-integration-ccx"></a>CLR tümleştirme (C + +/ CX)
Bazı Windows çalışma zamanı türleri özel işlem C + alma +/ CX ve dilleri (CLR) ortak dil çalışma zamanı temel alır. Bu makalede, başka bir dil için nasıl birden fazla dilde harita açıklanmaktadır. Örneğin, CLR Windows.Foundation.IVector eşlendiğini System.Collections.IList, Windows.Foundation.IMap System.Collections.IDictionary ve benzeri. Benzer şekilde, C + +/ CX türleri Platform::Delegate ve Platform::String gibi özel haritaları.  
  
## <a name="mapping-the-windows-runtime-to-ccx"></a>Windows çalışma zamanı eşlemesi C + +/ CX  
 C + olduğunda +/ CX okuyan bir Windows meta veri (.winmd) dosyası, derleyici otomatik olarak ortak Windows çalışma zamanı ad alanları ve türler C + eşler +/ CX ad alanları ve türler. Örneğin, sayısal Windows çalışma zamanı türü `UInt32` otomatik olarak eşlenir `default::uint32`.  
  
 C + +/ CX çeşitli diğer Windows çalışma zamanı türlerine eşlenir **Platform** ad alanı. Örneğin, **Windows::Foundation** salt Unicode metin dizesini temsil eden HSTRING tanıtıcısına eşlendi C + +/ CX `Platform::String` sınıfı. Bir Windows çalışma zamanı işlemi HRESULT hatası döndürdüğünde, C + eşlenmiş +/ CX `Platform::Exception`. Daha fazla bilgi için [yerleşik türler](https://msdn.microsoft.com/acc196fd-09da-4882-b554-6c94685ec75f).  
  
 C + +/ CX türünün işlevselliğini geliştirmek için belirli Windows çalışma zamanı ad alanlarında türleri de eşler. Bu tür için C + +/ CX Yardımcısı oluşturucular ve C++ için özeldir ve tür standart .winmd dosyasında kullanılamaz yöntemleri sağlar.  
  
 Aşağıdaki listelerde, yeni oluşturucular ve yardımcı yöntemler destekleyen değeri yapılar gösterilir. Başlatma listeleri yapı kullanan kod daha önce yazmış, yeni eklenen oluşturucular kullanacak şekilde değiştirin.  
  
 **Windows::Foundation**  
  
-   Noktası  
  
-   Rect  
  
-   Boyut  
  
 **Windows::UI**  
  
-   Renk  
  
 **Windows::UI::Xaml**  
  
-   CornerRadius  
  
-   Süresi  
  
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
 Visual C++ ya da C# Derleyicileri bir .winmd dosyası okunamıyor, bunlar otomatik olarak belirli türlerini meta veri dosyasında uygun C + harita +/ CX veya CLR türü. Örneğin, CLR Ivector içinde\<T > arabirimi için IList eşlenen\<T >. Ancak C + +/ CX, Ivector\<T > arabirimini başka bir türe eşlenmedi.  
  
 IReference\<T > Windows çalışma zamanı'nda eşler için Nullable\<T > .NET içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Diğer dillerle birlikte çalışma](../cppcx/interoperating-with-other-languages-c-cx.md)