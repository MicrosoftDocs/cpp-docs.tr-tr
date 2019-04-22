---
title: Arabirim öznitelikleri (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
ms.openlocfilehash: 8218ccb66c6be9edef5d7de751a73bf4753d069f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027211"
---
# <a name="interface-attributes"></a>Arabirim Öznitelikleri

Aşağıdaki öznitelikler uygulamak [arabirimi (veya __interface)](../../cpp/interface.md) C++ anahtar sözcüğü.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[async_uuid](async-uuid.md)|COM arabirimi zaman uyumlu ve zaman uyumsuz sürümlerini tanımlamak için MIDL derleyicisi yönergelerinin sağlandığı UUID belirtir.|
|[custom](custom-cpp.md)|Kendi özniteliklerine tanımlamanızı sağlar.|
|[dispinterface](dispinterface.md)|Bir arabirim gönderme arabirimi olarak .idl dosyasına yerleştirir.|
|[dual](dual.md)|Bir arabirim çift arabirim .idl dosyasına yerleştirir.|
|[export](export.md)|Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.|
|[helpcontext](helpcontext.md)|Kullanıcı Yardım dosyasında bu öğe hakkındaki bilgileri görüntüleme sağlayan bir bağlam kimliği belirtir.|
|[helpfile](helpfile.md)|Bir tür kitaplığı için Yardım dosyasına adını ayarlar.|
|[helpstring](helpstring.md)|Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir.|
|[helpstringcontext](helpstringcontext.md)|Bir .hlp veya .chm dosyasında bir Yardım konusu Kimliğini belirtir.|
|[helpstringdll](helpstringdll.md)|Belge dize arama (yerelleştirme) gerçekleştirmek için kullanılacak DLL'in adını belirtir.|
|[hidden](hidden.md)|Öğe var ancak kullanıcıya dayalı tarayıcıda görüntülenmemesi gerektiğini belirtir.|
|[library_block](library-block.md)|.İdl dosyasının kitaplığı bloğu içinde bir yapısı yerleştirir.|
|[local](local-cpp.md)|MIDL derleyicisi arabirimi başlığı kullanıldığında bir üstbilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saptamalar oluşturulan yerel bir yordam belirler.|
|[nonextensible](nonextensible.md)|Belirten `IDispatch` uygulaması yalnızca özellikleri içerir ve yöntemleri arabirimi açıklamasında listelenir ve çalışma zamanında ek üyeleriyle genişletilemez. Bu öznitelik yalnızca geçerli bir [çift](dual.md) arabirimi.|
|[odl](odl.md)|Arabirimdeki bir nesne Açıklama Dili (ODL) arabirim tanımlar.|
|[object](object-cpp.md)|Özel bir arabirim tanımlar.|
|[oleautomation](oleautomation.md)|Bir arabirim otomasyon ile uyumlu olduğunu gösterir.|
|[pointer_default](pointer-default.md)|Görünen üst düzey işaretçileri dışındaki tüm işaretçiler için varsayılan işaretçi öznitelik parametre listelerindeki belirtir.|
|[ptr](ptr.md)|Bir işaretçinin tam bir işaretçi olarak belirler.|
|[restricted](restricted.md)|Hangi üyelerin kitaplığının rasgele çağrılamaz belirler.|
|[uuid](uuid-cpp-attributes.md)|Kitaplık için benzersiz kimliği sağlar|

Bu kurallar, bir arabirim tanımlamak için uymanız gerekir:

- Çağırma kuralı varsayılan [__stdcall](../../cpp/stdcall.md).

- Bir belirtmezseniz sizin için bir GUID sağlanır.

- Hiçbir aşırı yüklenmiş yöntemler izin verilir.

Değil belirtirken [UUID](uuid-cpp-attributes.md) özniteliği ve farklı öznitelik projelerde aynı arabirimi adı kullanarak, aynı GUID oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıma Göre Öznitelikler](attributes-by-usage.md)