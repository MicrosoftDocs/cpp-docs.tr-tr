---
title: Arabirim öznitelikleri (C++ com)
ms.date: 10/02/2018
helpviewer_keywords:
- attributes [C++/CLI], reference topics
- interface attributes
ms.assetid: 27fcdfee-abce-4585-8b53-ee31635356e8
ms.openlocfilehash: 81a88ddfd74f20fa57ef615c988ba9786f41c1ad
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214831"
---
# <a name="interface-attributes"></a>Arabirim Öznitelikleri

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

[Kullanıma Göre Öznitelikler](attributes-by-usage.md)
