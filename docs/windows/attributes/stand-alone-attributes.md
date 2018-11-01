---
title: Tek başına öznitelikler (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
ms.openlocfilehash: 1183d2b171a25b3b2d1aef14c19f81be65effc6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640836"
---
# <a name="stand-alone-attributes"></a>Tek Başına Öznitelikler

Tek başına öznitelik C++ anahtar sözcüğü çalışmaz, ancak bir kod satırı gibi daha fazla. Tek başına öznitelik deyimleri noktalı virgül satırın sonunda gerektirir.

## <a name="stand-alone-attribute-list"></a>Tek başına öznitelik listesi

|Öznitelik|Açıklama|
|---------------|-----------------|
|[cpp_quote](cpp-quote.md)|Belirtilen dizeyi tırnak karakterleri olmadan oluşturulan üst bilgi dosyasına yayar.|
|[custom](custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[db_command](db-command.md)|OLE DB komut oluşturur.|
|[emitidl](emitidl.md)|Tüm sonraki IDL öznitelikleri işlem görüp oluşturulan .idl dosyasında yerleştirilmiş olup olmadığını belirler.|
|[idl_module](idl-module.md)|Bir giriş noktası bir DLL içinde belirtir.|
|[idl_quote](idl-quote.md)|Visual C++'ın geçerli sürümünde desteklenmeyen IDL yapıları kullanmanıza olanak tanır ve bunları oluşturulan .idl dosyasına geçirir.|
|[import](import.md)|Ana .idl dosyanızdan başvurmak istediğiniz tanımlarını içeren başka bir .idl, .odl veya .h dosyasını belirtir.|
|[importidl](importidl.md)|Belirtilen .idl dosyasının oluşturulan .idl dosyasına ekler.|
|[importlib](importlib.md)|Zaten başka bir tür kitaplığına oluşturulan tür kitaplığı için kullanılabilir derlenmiştir türleri sağlar.|
|[include](include-cpp.md)|Oluşturulan .idl dosyasına eklenecek bir veya daha fazla üst bilgi dosyaları belirtir.|
|[includelib](includelib-cpp.md)|Oluşturulan .idl dosyasına eklenecek bir .idl veya .h dosyası neden olur.|
|[library_block](library-block.md)|.İdl dosyasının kitaplığı bloğu içinde bir yapısı yerleştirir.|
|[module](module-cpp.md)|Kitaplık blok .idl dosyasında tanımlar.|
|[no_injected_text](no-injected-text.md)|Derleyici, özellik kullanımı sonucu olarak kod ekleme öğesinden engeller.|
|[pragma](pragma.md)|Belirtilen dizeyi tırnak karakterleri olmadan oluşturulan .idl dosyasına yayar.|

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıma Göre Öznitelikler](attributes-by-usage.md)