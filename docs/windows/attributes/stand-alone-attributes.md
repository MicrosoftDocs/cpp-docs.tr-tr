---
description: 'Hakkında daha fazla bilgi edinin: Stand-Alone öznitelikleri'
title: Stand-Alone öznitelikleri (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
ms.openlocfilehash: 39b7356243f9b6ba7c42e907ca0733f59b85961e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329598"
---
# <a name="stand-alone-attributes"></a>Tek Başına Öznitelikler

Bağımsız bir öznitelik C++ anahtar sözcüğü üzerinde çalışmaz, ancak bir kod satırı gibidir. Tek başına öznitelik deyimleri satırın sonunda noktalı virgül gerektirir.

## <a name="stand-alone-attribute-list"></a>Tek başına öznitelik listesi

|Öznitelik|Açıklama|
|---------------|-----------------|
|[cpp_quote](cpp-quote.md)|Belirtilen dizeyi, tırnak karakterleri olmadan, oluşturulan üst bilgi dosyasına yayar.|
|[Özel](custom-cpp.md)|Kendi öznitelemenizi tanımlamanızı sağlar.|
|[db_command](db-command.md)|Bir OLE DB komutu oluşturur.|
|[emitidl](emitidl.md)|Sonraki tüm IDL özniteliklerinin işlenip işlenmeyeceğini ve oluşturulan. IDL dosyasına yerleştirilip yerleştirilmeyeceğini belirler.|
|[idl_module](idl-module.md)|DLL 'de bir giriş noktası belirtir.|
|[idl_quote](idl-quote.md)|Geçerli Visual C++ sürümünde desteklenmeyen IDL yapılarını kullanmanıza ve bunların oluşturulan. IDL dosyasına geçmesini sağlar.|
|[aktarmaya](import.md)|Main. IDL dosyanızda başvurmak istediğiniz tanımları içeren başka bir. IDL,. odl veya. h dosyasını belirtir.|
|[importidl](importidl.md)|Belirtilen. IDL dosyasını oluşturulan. IDL dosyasına ekler|
|[importlib](importlib.md)|Oluşturulan tür kitaplığı için kullanılabilir başka bir tür kitaplığına derlenmiş olan türleri oluşturur.|
|[içeriyor](include-cpp.md)|Oluşturulan. IDL dosyasına dahil edilecek bir veya daha fazla üst bilgi dosyasını belirtir.|
|[INCLUDELIB](includelib-cpp.md)|Oluşturulan. IDL dosyasına bir. IDL veya. h dosyasının eklenmesine neden olur.|
|[library_block](library-block.md)|. IDL dosyasının Kitaplık bloğunun içine bir yapı koyar.|
|[birimi](module-cpp.md)|. IDL dosyasında kitaplık bloğunu tanımlar.|
|[no_injected_text](no-injected-text.md)|Öznitelik kullanımı sonucu olarak derleyicinin ekleme kodundan yapılmasını engeller.|
|[pragma](pragma.md)|Belirtilen dizeyi, tırnak karakterleri olmadan, oluşturulan. IDL dosyasına yayar.|

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıma göre öznitelikler](attributes-by-usage.md)
