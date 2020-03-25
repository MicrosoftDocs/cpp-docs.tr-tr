---
title: Kullanıma Göre Öznitelikler
ms.custom: index-page
ms.date: 10/02/2018
ms.topic: conceptual
helpviewer_keywords:
- attributes [C++/CLI]
ms.assetid: 8be2de10-b1ff-4ca4-a114-75318408593c
ms.openlocfilehash: fd5c5826b4119409dd288d0587c3e53a7d3f3aab
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167400"
---
# <a name="attributes-by-usage"></a>Kullanıma Göre Öznitelikler

Bu konu, özniteliklerini, C++ uygulandıkları dil öğelerine göre listeler.

Öznitelik, özniteliğin kapsamında olmayan bir öğeden önce geliyorsa öznitelik bloğu bir açıklama olarak değerlendirilir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[Modül Öznitelikleri](module-attributes.md)|[Modül](module-cpp.md) özniteliği için geçerlidir.|
|[Arabirim Öznitelikleri](interface-attributes.md)|[__İnterface](../../cpp/interface.md) C++ anahtar sözcüğü için geçerlidir.|
|[Sınıf Öznitelikleri](class-attributes.md)|C++ Anahtar sözcüğü için geçerlidir.|
|[Yöntem Öznitelikleri](method-attributes.md)|Bir sınıf, coclass veya arabirimdeki yöntemler için geçerlidir.|
|[Parametre Öznitelikleri](parameter-attributes.md)|Bir sınıftaki veya arabirimdeki bir yöntemin parametreleri için geçerlidir.|
|[Veri Üyesi Öznitelikleri](data-member-attributes.md)|Bir sınıf, coclass veya arabirimdeki veri üyeleri için geçerlidir.|
|[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)|C++ Anahtar sözcükler için geçerlidir.|
|[Dizi Öznitelikleri](array-attributes.md)|Diziler veya `SAFEARRAY`s için geçerlidir.|
|[Tek Başına Öznitelikler](stand-alone-attributes.md)|Bir kod satırı gibi çalışır, ancak bir C++ anahtar sözcük üzerinde çalışmaz. Tek başına öznitelik deyimleri satırın sonunda noktalı virgül gerektirir.|
|[Özel Öznitelikler](custom-attributes-cpp.md)|Kullanıcının meta verileri genişlemesine izin verir.|

## <a name="module-attributes"></a>Modül Öznitelikleri
Aşağıdaki öznitelik yalnızca [module](module-cpp.md) özniteliğine uygulanabilir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[helpstringdll](helpstringdll.md)|Belge dizesi aramasını (Yerelleştirme) gerçekleştirmek için kullanılacak DLL 'in adını belirtir.|

## <a name="interface-attributes"></a>Arabirim Öznitelikleri

Aşağıdaki öznitelikler [Arabirim (veya __interface)](../../cpp/interface.md) C++ anahtar sözcüğü için geçerlidir.

|Öznitelik|Açıklama|
|---------------|-----------------|
|[async_uuid](async-uuid.md)|Bir COM arabiriminin hem zaman uyumlu hem de zaman uyumsuz sürümlerini tanımlamak için MıDL derleyicisini yönlendiren UUID 'yi belirtir.|
|[custom](custom-cpp.md)|Kendi öznitelerinizi tanımlamanıza olanak sağlar.|
|[dispinterface](dispinterface.md)|Bir arabirimi. IDL dosyasına bir dağıtım arabirimi olarak koyar.|
|[dual](dual.md)|. IDL dosyasına bir arabirimi çift arabirim olarak koyar.|
|[export](export.md)|Veri yapısının. IDL dosyasına yerleştirilmesine neden olur.|
|[helpcontext](helpcontext.md)|Kullanıcının Yardım dosyasında bu öğeyle ilgili bilgileri görüntülemesine imkan tanıyan bir bağlam KIMLIĞI belirtir.|
|[helpfile](helpfile.md)|Bir tür kitaplığı için yardım dosyasının adını ayarlar.|
|[helpstring](helpstring.md)|Uygulandığı öğeyi anlatmak için kullanılan bir karakter dizesini belirtir.|
|[helpstringcontext](helpstringcontext.md)|Bir. hlp veya. chm dosyasındaki Yardım konusunun KIMLIĞINI belirtir.|
|[helpstringdll](helpstringdll.md)|Belge dizesi aramasını (Yerelleştirme) gerçekleştirmek için kullanılacak DLL 'in adını belirtir.|
|[hidden](hidden.md)|Öğenin var olduğunu ancak kullanıcıya dayalı bir tarayıcıda gösterilmemelidir.|
|[library_block](library-block.md)|. IDL dosyasının Kitaplık bloğunun içine bir yapı koyar.|
|[local](local-cpp.md)|Arabirim üstbilgisinde kullanıldığında MıDL derleyicisini üst bilgi Oluşturucu olarak kullanmanıza olanak tanır. Tek bir işlevde kullanıldığında, hiçbir saplamalar üretilmeden önce bir yerel yordam belirler.|
|[nonextensible](nonextensible.md)|`IDispatch` uygulamasının yalnızca arabirim açıklamasında listelenen özellikleri ve yöntemleri içerdiğini belirtir ve çalışma zamanında ek üyelerle birlikte genişletilemez. Bu öznitelik yalnızca [ikili](dual.md) bir arabirimde geçerlidir.|
|[odl](odl.md)|Bir arabirimi nesne Açıklama Dili (ODL) arabirimi olarak tanımlar.|
|[object](object-cpp.md)|Özel bir arabirim tanımlar.|
|[oleautomation](oleautomation.md)|Bir arabirimin Otomasyon ile uyumlu olduğunu gösterir.|
|[pointer_default](pointer-default.md)|Parametre listelerinde görünen en üst düzey işaretçiler hariç tüm işaretçiler için varsayılan işaretçi özniteliğini belirtir.|
|[ptr](ptr.md)|Bir işaretçiyi tam bir işaretçi olarak belirler.|
|[restricted](restricted.md)|Kitaplığın hangi üyelerinin rastgele çağrlamayacağını belirtir.|
|[uuid](uuid-cpp-attributes.md)|Kitaplığın benzersiz KIMLIĞINI sağlar|

Bir arabirim tanımlamak için bu kuralları gözlemleyebilirsiniz:

- Varsayılan çağırma kuralı [__stdcall](../../cpp/stdcall.md).

- Bir GUID sağlamadıysanız sizin için bir GUID sağlanır.

- Aşırı yüklenmiş yöntemlere izin verilmez.

[UUID](uuid-cpp-attributes.md) özniteliğini belirtmemiş ve farklı öznitelik projelerinde aynı arabirim adını KULLANıRKEN aynı GUID oluşturulur.

## <a name="see-also"></a>Ayrıca bkz.

[COM ve .NET için C++ Öznitelikleri](cpp-attributes-com-net.md)<br/>
[Gruplara Göre Öznitelikler](attributes-by-group.md)<br/>
[Öznitelikler Alfabetik Başvurusu](attributes-alphabetical-reference.md)
