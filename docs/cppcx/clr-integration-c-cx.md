---
description: 'Daha fazla bilgi edinin: CLR tümleştirmesi (C++/CX)'
title: CLR Tümleştirme (C++/CX)
ms.date: 01/22/2017
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
ms.openlocfilehash: ae335168ee456f0461154ab48e9d92325fdc599b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190243"
---
# <a name="clr-integration-ccx"></a>CLR Tümleştirme (C++/CX)

Bazı Windows Çalışma Zamanı türler C++/CX ' te özel işleme ve ortak dil çalışma zamanı (CLR) tabanlı dilleri alır. Bu makalede, bir dildeki çeşitli türlerin başka bir dile nasıl eşlenme konusu açıklanmaktadır. Örneğin, CLR, Windows. Foundation. IVector ' i System. Collections. IList, Windows. Foundation. map ' e System. Collections. IDictionary 'e ve bu şekilde eşler. Benzer şekilde, C++/CX Platform::D elegate ve platform:: String gibi türleri özel olarak eşler.

## <a name="mapping-the-windows-runtime-to-ccx"></a>Windows Çalışma Zamanı C++/CX ile eşleme

C++/CX bir Windows meta veri (. winmd) dosyası okurken, derleyici ortak Windows Çalışma Zamanı ad alanlarını ve türlerini otomatik olarak C++/CX ad alanları ve türlerine eşler. Örneğin, sayısal Windows Çalışma Zamanı türü `UInt32` otomatik olarak öğesine eşlenir `default::uint32` .

C++/CX, diğer diğer Windows Çalışma Zamanı türlerini **Platform** ad alanına eşler. Örneğin, salt okunurdur Unicode metin dizesini temsil eden **Windows:: Foundation** HString tanıtıcısı, C++/CX `Platform::String` sınıfına eşlenir. Bir Windows Çalışma Zamanı işlemi HRESULT hatası döndürdüğünde bir C++/CX ile eşleştirilir `Platform::Exception` .

C++/CX Ayrıca türdeki işlevleri geliştirmek için Windows Çalışma Zamanı ad alanlarında belirli türleri eşler. C++/CX, bu türler için C++ ' a özel ve türün standart. winmd dosyasında kullanılamayan yardımcı oluşturucular ve yöntemler sağlar.

Aşağıdaki listeler, yeni oluşturucular ve yardımcı yöntemleri destekleyen değer yapılarını gösterir. Daha önce yapı başlatma listeleri kullanan kodu yazdıysanız, bunu yeni eklenen oluşturucuları kullanacak şekilde değiştirin.

**Windows:: Foundation**

- Seçeneğinin

- Rect

- Boyut

**Windows:: UI**

- Renk

**Windows:: UI:: xaml**

- Köşeli yarıçap

- Süre

- GridLength

- Kalınlık

**Windows:: UI:: XAML:: Interop**

- TypeName

**Windows:: UI:: XAML:: medya**

- Matris

**Windows:: UI:: XAML:: Media:: Animation**

- KeyTime

- RepeatBehavior

**Windows:: UI:: XAML:: Media:: Media3D**

- Matrix3D

## <a name="mapping-the-clr-to-ccx"></a>CLR 'yi C++/CX ile eşleme

Microsoft C++ veya C# derleyicileri bir. winmd dosyası okuduklarında, meta veri dosyasındaki belirli türleri uygun C++/CX veya CLR türlerine otomatik olarak eşler. Örneğin, CLR 'de, IVector \<T> arabirimi IList ile eşleştirilir \<T> . Ancak C++/CX ' te, IVector \<T> arabirimi başka bir türle eşlenmedi.

\<T>Windows çalışma zamanı Içindeki IReference, .net Içinde null yapılabilir ile eşlenir \<T> .

## <a name="see-also"></a>Ayrıca bkz.

[Diğer dillerle birlikte çalışma](../cppcx/interoperating-with-other-languages-c-cx.md)
