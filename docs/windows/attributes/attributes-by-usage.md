---
title: Kullanıma Göre Öznitelikler
ms.custom: index-page
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributes [C++/CLI]
ms.assetid: 8be2de10-b1ff-4ca4-a114-75318408593c
ms.openlocfilehash: dcbed019f8cd08ddbf4ab6b4756a59f7fcbabc4b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361329"
---
# <a name="attributes-by-usage"></a>Kullanıma Göre Öznitelikler

Bu konu, öznitelikleri uyguladıkları C++ dil öğelerine göre listeler.

Bir öznitelik öznitelik kapsamında olmayan bir öğe önce ise, öznitelik bloğu bir açıklama olarak kabul edilir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[Modül Öznitelikleri](module-attributes.md)|[Modül](module-cpp.md) özniteliği için geçerlidir.|
|[Arabirim Öznitelikleri](interface-attributes.md)|[C++](../../cpp/interface.md) anahtar __interface için geçerlidir.|
|[Sınıf Öznitelikleri](class-attributes.md)|C++ anahtar kelimesi için geçerlidir.|
|[Yöntem Öznitelikleri](method-attributes.md)|Bir sınıf, ortak sınıf veya arabirimdeki yöntemler için geçerlidir.|
|[Parametre Öznitelikleri](parameter-attributes.md)|Bir sınıf veya arabirimdeki bir yöntemin parametreleri için geçerlidir.|
|[Veri Üye Öznitelikleri](data-member-attributes.md)|Bir sınıfta, ortak sınıftaki veya arabirimdeki veri üyeleri için geçerlidir.|
|[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)|C++ anahtar kelimeleri için geçerlidir.|
|[Dizi Öznitelikleri](array-attributes.md)|Diziler veya `SAFEARRAY`s için geçerlidir.|
|[Tek Başına Öznitelikler](stand-alone-attributes.md)|Daha çok bir kod satırı gibi çalışır, ancak C++ anahtar sözcüğüüzerinde çalışmaz. Tek başına öznitelik deyimleri satırın sonunda bir yarı nokta üzerinde nokta gerektirir.|
|[Özel Öznitelikler](custom-attributes-cpp.md)|Kullanıcının meta verileri genişletmesine olanak tanır.|

## <a name="module-attributes"></a>Modül Öznitelikleri

Aşağıdaki öznitelik yalnızca [modül](module-cpp.md) özniteliğine uygulanabilir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[helpstringdll](helpstringdll.md)|Belge dizesi aramasını (yerelleştirme) gerçekleştirmek için kullanılacak DLL'nin adını belirtir.|

## <a name="interface-attributes"></a>Arabirim Öznitelikleri

Aşağıdaki öznitelikler [arabirim (veya __interface)](../../cpp/interface.md) C++ anahtar kelimesi için geçerlidir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[async_uuid](async-uuid.md)|BIR COM arabiriminin hem senkron hem de eşzamanlı sürümlerini tanımlamak için MIDL derleyicisini yönlendiren UUID'yi belirtir.|
|[Özel](custom-cpp.md)|Kendi özniteliklerinizi tanımlamanızı sağlar.|
|[dispinterface](dispinterface.md)|.idl dosyasına bir arabirim gönderir.|
|[dual](dual.md)|.idl dosyasına bir arabirim ilerler.|
|[Ihracat](export.md)|Bir veri yapısının .idl dosyasına yerleştirilmesine neden olur.|
|[helpcontext](helpcontext.md)|Kullanıcının Yardım dosyasındaki bu öğe hakkındaki bilgileri görüntülemesini sağlayan bir bağlam kimliği belirtir.|
|[helpfile](helpfile.md)|Tür kitaplığı için Yardım dosyasının adını ayarlar.|
|[helpstring](helpstring.md)|Uygulandığı öğeyi açıklamak için kullanılan bir karakter dizesini belirtir.|
|[helpstringcontext](helpstringcontext.md)|Bir .hlp veya .chm dosyasında bir yardım konusunun kimliğini belirtir.|
|[helpstringdll](helpstringdll.md)|Belge dizesi aramasını (yerelleştirme) gerçekleştirmek için kullanılacak DLL'nin adını belirtir.|
|[Gizli](hidden.md)|Öğenin var olduğunu, ancak kullanıcı yönelimli bir tarayıcıda görüntülenmemesi gerektiğini gösterir.|
|[library_block](library-block.md)|.idl dosyasının kitaplık bloğunun içine bir yapı yerleştirir.|
|[Yerel](local-cpp.md)|Arabirim üstbilgisinde kullanıldığında MIDL derleyicisini üstbilgi üreteci olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, saplama nın oluşturulmamasA için yerel bir yordam belirtir.|
|[nonextensible](nonextensible.md)|Uygulamanın `IDispatch` yalnızca arabirim açıklamasında listelenen özellikleri ve yöntemleri içerdiğini ve çalışma zamanında ek üyelerle genişletilemeyeceğini belirtir. Bu öznitelik yalnızca [çift](dual.md) arabirimde geçerlidir.|
|[odl](odl.md)|Arabirimi Nesne Açıklama Dili (ODL) arabirimi olarak tanımlar.|
|[Nesne](object-cpp.md)|Özel bir arabirim tanımlar.|
|[oleautomation](oleautomation.md)|Bir arabirimin Otomasyon ile uyumlu olduğunu gösterir.|
|[pointer_default](pointer-default.md)|Parametre listelerinde görünen üst düzey işaretçiler dışında tüm işaretçiler için varsayılan işaretçi özniteliğini belirtir.|
|[Ptr](ptr.md)|İşaretçiyi tam işaretçi olarak belirtir.|
|[kısıtlı](restricted.md)|Kitaplığın hangi üyelerinin rasgele çağrılamayacağını belirtir.|
|[uuid](uuid-cpp-attributes.md)|Kitaplık için benzersiz kimliği sağlar|

Arabirimi tanımlamak için aşağıdaki kurallara uymanız gerekir:

- Varsayılan arama kuralı [__stdcall.](../../cpp/stdcall.md)

- Bir guid tedarik etmezseniz sizin için verilir.

- Aşırı yüklenmiş yöntemlere izin verilmez.

[Uuid](uuid-cpp-attributes.md) özniteliği belirtilmediğinde ve farklı öznitelik projelerinde aynı arabirim adı kullanılmadığında, aynı GUID oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[COM ve .NET için C++ Öznitelikleri](cpp-attributes-com-net.md)<br/>
[Gruplara Göre Öznitelikler](attributes-by-group.md)<br/>
[Öznitelikler Alfabetik Başvurusu](attributes-alphabetical-reference.md)
