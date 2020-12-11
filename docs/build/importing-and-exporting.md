---
description: 'Hakkında daha fazla bilgi edinin: Içeri ve dışarı aktarma'
title: İçeri ve Dışarı Aktarma
ms.date: 05/06/2019
helpviewer_keywords:
- DLLs [C++], importing
- exporting DLLs [C++]
- importing DLLs [C++]
- DLLs [C++], exporting from
- __declspec(dllimport) keyword [C++]
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
ms.openlocfilehash: e2045b41450881056fb109f059e9c3202d93cab3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162527"
---
# <a name="importing-and-exporting"></a>İçeri ve Dışarı Aktarma

Ortak sembolleri bir uygulamaya aktarabilir veya iki yöntemi kullanarak bir DLL 'den işlevleri dışarı aktarabilirsiniz:

- DLL derlerken modül tanımı (. def) dosyası kullan

- **`__declspec(dllimport)`** Ana uygulamadaki anahtar sözcükleri veya **`__declspec(dllexport)`** bir işlev tanımını kullanın

## <a name="using-a-def-file"></a>. Def dosyası kullanma

Modül tanım (. def) dosyası, DLL 'nin çeşitli özniteliklerini tanımlayan bir veya daha fazla modül deyimi içeren bir metin dosyasıdır. **`__declspec(dllimport)`** **`__declspec(dllexport)`** DLL 'nin işlevlerini dışarı aktarmak için veya KULLANMıYORSANıZ, dll bir. def dosyası gerektirir.

. Def dosyalarını kullanarak [bir uygulamaya aktarabilir](importing-using-def-files.md) veya [bir dll 'den dışarı aktarabilirsiniz](exporting-from-a-dll-using-def-files.md).

## <a name="using-__declspec"></a>__Declspec kullanma

Kodunuzun doğru derlenmesi için kullanmanız gerekmez **`__declspec(dllimport)`** , ancak bunu yapmak derleyicinin daha iyi kod oluşturmasını sağlar. Derleyici, bir işlevin bir DLL içinde mevcut olup olmadığını belirleyebildiğinden daha iyi bir kod oluşturabilir, bu da derleyicinin bir DLL sınırındaki bir işlev çağrısında bulunan bir yöneltme düzeyini atlayan kod üretmesine olanak tanır. Ancak, **`__declspec(dllimport)`** BIR DLL 'de kullanılan değişkenleri içeri aktarmak için kullanmanız gerekir.

Uygun. def dosya dışarı aktarmaları bölümüyle, **`__declspec(dllexport)`** gerekli değildir. **`__declspec(dllexport)`** bir. exe veya. dll dosyasından. def dosyası kullanılmadan işlevleri dışarı aktarmanın kolay bir yolunu sağlamak için eklenmiştir.

Win32 Taşınabilir yürütülebilir biçimi, içeri aktarımları onarmak için dokunulmalıdır gereken sayfa sayısını en aza indirmek için tasarlanmıştır. Bunu yapmak için, Içeri aktarma adresi tablosu olarak adlandırılan tüm programlar için içeri aktarma adreslerini tek bir yerde yerleştirir. Bu, yükleyicinin bu içeri aktarımlara erişirken yalnızca bir veya iki sayfayı değiştirmesine izin verir.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Bir uygulamaya içeri aktarma](importing-into-an-application-using-declspec-dllimport.md)

- [DLL 'den dışarı aktarma](exporting-from-a-dll.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)
