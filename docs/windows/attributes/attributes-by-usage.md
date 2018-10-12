---
title: Kullanıma göre öznitelikler | Microsoft Docs
ms.custom: index-page
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++/CLI]
ms.assetid: 8be2de10-b1ff-4ca4-a114-75318408593c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 39dac1bda25a66ecd67feac167e0029931a204e0
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789993"
---
# <a name="attributes-by-usage"></a>Kullanıma Göre Öznitelikler

Bu konu, özniteliklere göre uygulandıkları C++ Dil öğelerini listeler.

Öznitelik özniteliğin kapsam içinde değil bir Visual C++ öğesi önceyse, öznitelik blok açıklama olarak kabul edilir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[Modül Öznitelikleri](module-attributes.md)|Uygulandığı [Modülü](module-cpp.md) özniteliği.|
|[Arabirim Öznitelikleri](interface-attributes.md)|Uygulandığı [__interface](../../cpp/interface.md) C++ anahtar sözcüğü.|
|[Sınıf Öznitelikleri](class-attributes.md)|C++ anahtar sözcüğü için geçerlidir.|
|[Yöntem Öznitelikleri](method-attributes.md)|Bir sınıf, coclass'ı veya arabirim yöntemleri için geçerlidir.|
|[Parametre Öznitelikleri](parameter-attributes.md)|Bir sınıf veya arabirim yönteminin parametreleri geçerlidir.|
|[Veri Üyesi Öznitelikleri](data-member-attributes.md)|Veri üyeleri sınıf, coclass'ı veya arabirim uygular.|
|[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)|C++ anahtar sözcükleri için geçerlidir.|
|[Dizi Öznitelikleri](array-attributes.md)|Diziler için geçerlidir veya `SAFEARRAY`s.|
|[Tek Başına Öznitelikler](stand-alone-attributes.md)|Bir kod satırı gibi çalışır, ancak C++ anahtar sözcüğü çalışmaz. Tek başına öznitelik deyimleri noktalı virgül satırın sonunda gerektirir.|
|[Özel öznitelikler](custom-attributes-cpp.md)|Meta verileri genişletme izin verir.|

## <a name="module-attributes"></a>Modül Öznitelikleri
Aşağıdaki özniteliği için yalnızca uygulanabilir [Modülü](module-cpp.md) özniteliği.
  
|Öznitelik|Açıklama|
|---------------|-----------------|
|[helpstringdll](helpstringdll.md)|Belge dize arama (yerelleştirme) gerçekleştirmek için kullanılacak DLL'in adını belirtir.|

## <a name="interface-attributes"></a>Arabirim Öznitelikleri

Aşağıdaki öznitelikler uygulamak [arabirimi (veya __interface)](../../cpp/interface.md) C++ anahtar sözcüğü.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[async_uuid](async-uuid.md)|COM arabirimi zaman uyumlu ve zaman uyumsuz sürümlerini tanımlamak için MIDL derleyicisi yönergelerinin sağlandığı UUID belirtir.|
|[Özel](custom-cpp.md)|Kendi özniteliklerine tanımlamanızı sağlar.|
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
|[Yerel](local-cpp.md)|MIDL derleyicisi arabirimi başlığı kullanıldığında bir üstbilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saptamalar oluşturulan yerel bir yordam belirler.|
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


## <a name="see-also"></a>Ayrıca Bkz.

[COM ve .NET için C++ öznitelikleri](cpp-attributes-com-net.md)<br/>
[Gruplara Göre Öznitelikler](attributes-by-group.md)<br/>
[Öznitelikler Alfabetik Başvurusu](attributes-alphabetical-reference.md)