---
title: CLR tümleştirmesi (C++/CX)
ms.date: 01/22/2017
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
ms.openlocfilehash: 44ef35d1a62706cae37285c06547a8b9b7deb35c
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740287"
---
# <a name="clr-integration-ccx"></a>CLR tümleştirmesi (C++/CX)

Bazı Windows Çalışma Zamanı türler,/CX 'de C++özel işleme ve ortak dil çalışma ZAMANıNı (CLR) temel alan dilleri alır. Bu makalede, bir dildeki çeşitli türlerin başka bir dile nasıl eşlenme konusu açıklanmaktadır. Örneğin, CLR, Windows. Foundation. IVector ' i System. Collections. IList, Windows. Foundation. map ' e System. Collections. IDictionary 'e ve bu şekilde eşler. Benzer şekilde C++,/CX Platform::D elegate ve platform:: String gibi özel olarak haritalar türleri.

## <a name="mapping-the-windows-runtime-to-ccx"></a>Windows Çalışma Zamanı/CX ile C++eşleme

C++/CX bir Windows meta veri (. winmd) dosyası okuduğunda, derleyici ortak Windows çalışma zamanı ad alanlarını ve türlerini otomatik olarak C++/CX ad alanları ve türlerine eşler. Örneğin, sayısal Windows çalışma zamanı türü `UInt32` otomatik olarak öğesine `default::uint32`eşlenir.

C++/CX, diğer birçok Windows Çalışma Zamanı türünü **Platform** ad alanına eşler. Örneğin, salt okunurdur Unicode metin dizesini temsil eden **Windows:: Foundation** HString tanıtıcısı, C++/CX `Platform::String` sınıfına eşlenir. Bir Windows Çalışma Zamanı işlemi HRESULT hatası döndürdüğünde, bir C++/CX `Platform::Exception`ile eşleştirilir.

Ayrıca C++,/CX, türdeki işlevleri geliştirmek için Windows çalışma zamanı ad alanlarında belirli türleri de eşler. Bu türler için, C++/CX, türün standart. winmd dosyasında bulunmayan ve öğesine C++ özgü yardımcı oluşturucular ve yöntemler sağlar.

Aşağıdaki listeler, yeni oluşturucular ve yardımcı yöntemleri destekleyen değer yapılarını gösterir. Daha önce yapı başlatma listeleri kullanan kodu yazdıysanız, bunu yeni eklenen oluşturucuları kullanacak şekilde değiştirin.

**Windows:: Foundation**

- Seçeneğinin

- Rect

- Boyut

**Windows:: UI**

- Renk

**Windows::UI::Xaml**

- Köşeli yarıçap

- Duration

- GridLength

- Kalınlığı

**Windows::UI::Xaml::Interop**

- TypeName

**Windows::UI::Xaml::Media**

- Matrisin

**Windows::UI::Xaml::Media::Animation**

- KeyTime

- RepeatBehavior

**Windows::UI::Xaml::Media::Media3D**

- Matrix3D

## <a name="mapping-the-clr-to-ccx"></a>CLR 'yi/CX ile C++eşleme

Microsoft C++ veya C# derleyiciler bir. winmd dosyasını okuduklarında, meta veri dosyasındaki belirli TÜRLERI uygun C++/CX veya clr türlerine otomatik olarak eşler. Örneğin, clr 'de, IVector\<T > arabirimi IList\<t > ile eşlenir. Ancak/CX C++'de, IVector\<T > arabirimi başka bir türle eşlenmedi.

Windows çalışma zamanı içindeki\<IReference t >, .net 'teki Nullable\<t > ile eşlenir.

## <a name="see-also"></a>Ayrıca bkz.

[Diğer Dillerle Birlikte Çalışma](../cppcx/interoperating-with-other-languages-c-cx.md)
