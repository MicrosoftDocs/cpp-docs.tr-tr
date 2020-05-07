---
title: İçeri ve Dışarı Aktarma
ms.date: 05/06/2019
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
ms.openlocfilehash: 03931f7f128ab0666890bb8e76677db67dda8fc7
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220633"
---
# <a name="importing-and-exporting"></a>İçeri ve Dışarı Aktarma

Ortak sembolleri bir uygulamaya aktarabilir veya iki yöntemi kullanarak bir DLL 'den işlevleri dışarı aktarabilirsiniz:

- DLL derlerken modül tanımı (. def) dosyası kullan

- Ana uygulamadaki bir işlev tanımında **__declspec (dllimport)** veya **__declspec (dllexport)** anahtar sözcüklerini kullanın

## <a name="using-a-def-file"></a>. Def dosyası kullanma

Modül tanım (. def) dosyası, DLL 'nin çeşitli özniteliklerini tanımlayan bir veya daha fazla modül deyimi içeren bir metin dosyasıdır. DLL 'nin işlevlerini dışarı aktarmak için **__declspec (dllimport)** veya **__declspec (dllexport)** kullanmıyorsanız, dll bir. def dosyası gerektirir.

. Def dosyalarını kullanarak [bir uygulamaya aktarabilir](importing-using-def-files.md) veya [bir dll 'den dışarı aktarabilirsiniz](exporting-from-a-dll-using-def-files.md).

## <a name="using-__declspec"></a>__Declspec kullanma

Kodunuzun doğru derlenmesi için **__declspec (dllimport)** kullanmanız gerekmez, ancak bunu yapmak derleyicinin daha iyi kod oluşturmasını sağlar. Derleyici, bir işlevin bir DLL içinde mevcut olup olmadığını belirleyebildiğinden daha iyi bir kod oluşturabilir, bu da derleyicinin bir DLL sınırındaki bir işlev çağrısında bulunan bir yöneltme düzeyini atlayan kod üretmesine olanak tanır. Ancak, bir DLL 'de kullanılan değişkenleri içeri aktarmak için **__declspec (dllimport)** kullanmanız gerekir.

Uygun. def dosya dışarı aktarmaları bölümüyle **__declspec (dllexport)** gerekli değildir. bir. exe veya. dll dosyasından. def dosyası kullanılmadan işlevleri dışarı aktarmanın kolay bir yolunu sağlamak için **__declspec (dllexport)** eklenmiştir.

Win32 Taşınabilir yürütülebilir biçimi, içeri aktarımları onarmak için dokunulmalıdır gereken sayfa sayısını en aza indirmek için tasarlanmıştır. Bunu yapmak için, Içeri aktarma adresi tablosu olarak adlandırılan tüm programlar için içeri aktarma adreslerini tek bir yerde yerleştirir. Bu, yükleyicinin bu içeri aktarımlara erişirken yalnızca bir veya iki sayfayı değiştirmesine izin verir.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir uygulamaya içeri aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 'den dışarı aktarma](exporting-from-a-dll.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)
