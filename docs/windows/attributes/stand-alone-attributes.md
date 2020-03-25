---
title: Tek başına öznitelikler (C++ com)
ms.date: 10/02/2018
helpviewer_keywords:
- standalone attributes
- attributes [C++/CLI], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
ms.openlocfilehash: a7df91bbb1c6929b08d8cd867be9f13ce0c35b91
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166178"
---
# <a name="stand-alone-attributes"></a>Tek Başına Öznitelikler

Bağımsız bir öznitelik bir C++ anahtar sözcük üzerinde çalışmaz, ancak bir kod satırı gibidir. Tek başına öznitelik deyimleri satırın sonunda noktalı virgül gerektirir.

## <a name="stand-alone-attribute-list"></a>Tek başına öznitelik listesi

|Öznitelik|Açıklama|
|---------------|-----------------|
|[cpp_quote](cpp-quote.md)|Belirtilen dizeyi, tırnak karakterleri olmadan, oluşturulan üst bilgi dosyasına yayar.|
|[custom](custom-cpp.md)|Kendi öznitelemenizi tanımlamanızı sağlar.|
|[db_command](db-command.md)|Bir OLE DB komutu oluşturur.|
|[emitidl](emitidl.md)|Sonraki tüm IDL özniteliklerinin işlenip işlenmeyeceğini ve oluşturulan. IDL dosyasına yerleştirilip yerleştirilmeyeceğini belirler.|
|[idl_module](idl-module.md)|DLL 'de bir giriş noktası belirtir.|
|[idl_quote](idl-quote.md)|Geçerli Visual C++ sürümünde desteklenmeyen IDL yapılarını kullanmanıza ve bunların oluşturulan. IDL dosyasına geçmesini sağlar.|
|[import](import.md)|Main. IDL dosyanızda başvurmak istediğiniz tanımları içeren başka bir. IDL,. odl veya. h dosyasını belirtir.|
|[importidl](importidl.md)|Belirtilen. IDL dosyasını oluşturulan. IDL dosyasına ekler|
|[importlib](importlib.md)|Oluşturulan tür kitaplığı için kullanılabilir başka bir tür kitaplığına derlenmiş olan türleri oluşturur.|
|[include](include-cpp.md)|Oluşturulan. IDL dosyasına dahil edilecek bir veya daha fazla üst bilgi dosyasını belirtir.|
|[includelib](includelib-cpp.md)|Oluşturulan. IDL dosyasına bir. IDL veya. h dosyasının eklenmesine neden olur.|
|[library_block](library-block.md)|. IDL dosyasının Kitaplık bloğunun içine bir yapı koyar.|
|[module](module-cpp.md)|. IDL dosyasında kitaplık bloğunu tanımlar.|
|[no_injected_text](no-injected-text.md)|Öznitelik kullanımı sonucu olarak derleyicinin ekleme kodundan yapılmasını engeller.|
|[pragma](pragma.md)|Belirtilen dizeyi, tırnak karakterleri olmadan, oluşturulan. IDL dosyasına yayar.|

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıma Göre Öznitelikler](attributes-by-usage.md)
