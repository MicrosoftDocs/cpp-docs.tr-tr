---
title: Tek başına öznitelikler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- standalone attributes
- attributes [C++], standalone
ms.assetid: 0d72e84e-236c-43b3-ac9a-d9b91fcd6794
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6562a1de8baa9a5805f044233b97bf8dd8840638
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613764"
---
# <a name="stand-alone-attributes"></a>Tek Başına Öznitelikler
Tek başına öznitelik C++ anahtar sözcüğü çalışmaz, ancak bir kod satırı gibi daha fazla. Tek başına öznitelik deyimleri noktalı virgül satırın sonunda gerektirir.
  
|Öznitelik|Açıklama|
|---------------|-----------------|
|[cpp_quote](../windows/cpp-quote.md)|Belirtilen dizeyi tırnak karakterleri olmadan oluşturulan üst bilgi dosyasına yayar.|
|[Özel](../windows/custom-cpp.md)|Kendi özniteliğinizi tanımlamanızı sağlar.|
|[db_command](../windows/db-command.md)|OLE DB komut oluşturur.|
|[emitidl](../windows/emitidl.md)|Tüm sonraki IDL öznitelikleri işlem görüp oluşturulan .idl dosyasında yerleştirilmiş olup olmadığını belirler.|
|[idl_module](../windows/idl-module.md)|Bir giriş noktası bir DLL içinde belirtir.|
|[idl_quote](../windows/idl-quote.md)|Visual C++'ın geçerli sürümünde desteklenmeyen IDL yapıları kullanmanıza olanak tanır ve bunları oluşturulan .idl dosyasına geçirir.|
|[import](../windows/import.md)|Ana .idl dosyanızdan başvurmak istediğiniz tanımlarını içeren başka bir .idl, .odl veya .h dosyasını belirtir.|
|[importidl](../windows/importidl.md)|Belirtilen .idl dosyasının oluşturulan .idl dosyasına ekler.|
|[importlib](../windows/importlib.md)|Zaten başka bir tür kitaplığına oluşturulan tür kitaplığı için kullanılabilir derlenmiştir türleri sağlar.|
|[İçerir](../windows/include-cpp.md)|Oluşturulan .idl dosyasına eklenecek bir veya daha fazla üst bilgi dosyaları belirtir.|
|[includelib](../windows/includelib-cpp.md)|Oluşturulan .idl dosyasına eklenecek bir .idl veya .h dosyası neden olur.|
|[library_block](../windows/library-block.md)|.İdl dosyasının kitaplığı bloğu içinde bir yapısı yerleştirir.|
|[Modülü](../windows/module-cpp.md)|Kitaplık blok .idl dosyasında tanımlar.|
|[no_injected_text](../windows/no-injected-text.md)|Derleyici, özellik kullanımı sonucu olarak kod ekleme öğesinden engeller.|
|[pragma](../windows/pragma.md)|Belirtilen dizeyi tırnak karakterleri olmadan oluşturulan .idl dosyasına yayar.|
  
## <a name="see-also"></a>Ayrıca Bkz.
 [Kullanıma Göre Öznitelikler](../windows/attributes-by-usage.md)