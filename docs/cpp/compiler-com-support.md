---
title: Derleyici COM Desteği
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
ms.openlocfilehash: 6ab697e5a090158b034a385e60978cff4a73f488
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857586"
---
# <a name="compiler-com-support"></a>Derleyici COM Desteği

**Microsoft 'a özgü**

Microsoft C++ derleyicisi, bileşen nesne MODELI (com) tür kitaplıklarını doğrudan okuyabilir ve içeriği derlemeye eklenebilecek C++ kaynak koda çevirebilir. Dil uzantıları, masaüstü uygulamalarına yönelik istemci tarafında COM programlamayı kolaylaştırmak için kullanılabilir.

[#İmport Önişlemci yönergesini](../preprocessor/hash-import-directive-cpp.md)kullanarak, derleyici bir tür kitaplığını OKUYABILIR ve com arabirimlerini sınıflar olarak açıklayan bir C++ üstbilgi dosyasına dönüştürebilir. Ortaya çıkan tür kitaplığı üstbilgi dosyaları için içeriğin Kullanıcı denetimi için bir dizi `#import` özniteliği vardır.

Bir COM nesnesine bir genel benzersiz tanımlayıcı (GUID) atamak için [__declspec](../cpp/declspec.md) genişletilmiş öznitelik [UUID](../cpp/uuid-cpp.md) 'sini kullanabilirsiniz. Anahtar sözcüğü [__uuidof](../cpp/uuidof-operator.md) bir com NESNESIYLE ilişkili GUID 'yi ayıklamak için kullanılabilir. Bir COM nesnesinin veri üyesi için `get` ve `set` yöntemlerini belirtmek için başka bir **__declspec** özniteliği, [özelliği](../cpp/property-cpp.md)kullanılabilir.

`VARIANT` ve `BSTR` türlerini desteklemek, akıllı işaretçiler uygulamak ve `_com_raise_error`tarafından oluşturulan hata nesnesini kapsüllemek için bir COM desteği genel işlevleri ve sınıfları kümesi verilmiştir:

- [Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)

- [_bstr_t](../cpp/bstr-t-class.md)

- [_com_error](../cpp/com-error-class.md)

- [_com_ptr_t](../cpp/com-ptr-t-class.md)

- [_variant_t](../cpp/variant-t-class.md)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)<br/>
[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)
