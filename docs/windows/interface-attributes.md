---
title: Arabirim öznitelikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 850646e2dda1f226eff7c921dd3fe9f85595ca69
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317660"
---
# <a name="interface-attributes"></a>Arabirim Öznitelikleri

Aşağıdaki öznitelikler uygulamak [arabirimi (veya __interface)](../cpp/interface.md) C++ anahtar sözcüğü.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[async_uuid](../windows/async-uuid.md)|COM arabirimi zaman uyumlu ve zaman uyumsuz sürümlerini tanımlamak için MIDL derleyicisi yönergelerinin sağlandığı UUID belirtir.|
|[Özel](../windows/custom-cpp.md)|Kendi özniteliklerine tanımlamanızı sağlar.|
|[dispinterface](../windows/dispinterface.md)|Bir arabirim gönderme arabirimi olarak .idl dosyasına yerleştirir.|
|[dual](../windows/dual.md)|Bir arabirim çift arabirim .idl dosyasına yerleştirir.|
|[export](../windows/export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[helpcontext](../windows/helpcontext.md)|Kullanıcı Yardım dosyasında bu öğe hakkındaki bilgileri görüntüleme sağlayan bir bağlam kimliği belirtir.|
|[helpfile](../windows/helpfile.md)|Bir tür kitaplığı için Yardım dosyasına adını ayarlar.|
|[helpstring](../windows/helpstring.md)|Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir.|
|[helpstringcontext](../windows/helpstringcontext.md)|Bir .hlp veya .chm dosyasında bir Yardım konusu Kimliğini belirtir.|
|[helpstringdll](../windows/helpstringdll.md)|Belge dize arama (yerelleştirme) gerçekleştirmek için kullanılacak DLL'in adını belirtir.|
|[hidden](../windows/hidden.md)|Öğe var ancak kullanıcıya dayalı tarayıcıda görüntülenmemesi gerektiğini belirtir.|
|[library_block](../windows/library-block.md)|.İdl dosyasının kitaplığı bloğu içinde bir yapısı yerleştirir.|
|[Yerel](../windows/local-cpp.md)|MIDL derleyicisi arabirimi başlığı kullanıldığında bir üstbilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saptamalar oluşturulan yerel bir yordam belirler.|
|[nonextensible](../windows/nonextensible.md)|Belirten `IDispatch` uygulaması yalnızca özellikleri içerir ve yöntemleri arabirimi açıklamasında listelenir ve çalışma zamanında ek üyeleriyle genişletilemez. Bu öznitelik yalnızca geçerli bir [çift](../windows/dual.md) arabirimi.|
|[odl](../windows/odl.md)|Arabirimdeki bir nesne Açıklama Dili (ODL) arabirim tanımlar.|
|[object](../windows/object-cpp.md)|Özel bir arabirim tanımlar.|
|[oleautomation](../windows/oleautomation.md)|Bir arabirim otomasyon ile uyumlu olduğunu gösterir.|
|[pointer_default](../windows/pointer-default.md)|Görünen üst düzey işaretçileri dışındaki tüm işaretçiler için varsayılan işaretçi öznitelik parametre listelerindeki belirtir.|
|[ptr](../windows/ptr.md)|Bir işaretçinin tam bir işaretçi olarak belirler.|
|[restricted](../windows/restricted.md)|Hangi üyelerin kitaplığının rasgele çağrılamaz belirler.|
|[uuid](../windows/uuid-cpp-attributes.md)|Kitaplık için benzersiz kimliği sağlar|

Bu kurallar, bir arabirim tanımlamak için uymanız gerekir:

- Çağırma kuralı varsayılan [__stdcall](../cpp/stdcall.md).

- Bir belirtmezseniz sizin için bir GUID sağlanır.

- Hiçbir aşırı yüklenmiş yöntemler izin verilir.

Değil belirtirken [UUID](../windows/uuid-cpp-attributes.md) özniteliği ve farklı öznitelik projelerde aynı arabirimi adı kullanarak, aynı GUID oluşturulur.

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıma Göre Öznitelikler](../windows/attributes-by-usage.md)