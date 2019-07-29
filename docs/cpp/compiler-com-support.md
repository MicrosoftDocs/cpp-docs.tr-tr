---
title: Derleyici COM Desteği
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
ms.openlocfilehash: 421930088dcbf9762d50b5af37d994b9008890eb
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606384"
---
# <a name="compiler-com-support"></a>Derleyici COM Desteği

## <a name="microsoft-specific"></a>Microsoft'a Özgü

Microsoft C++ derleyicisi, bileşen nesne MODELI (com) tür kitaplıklarını doğrudan okuyabilir ve içeriği derlemeye eklenebilecek C++ kaynak koda çevirebilir. Dil uzantıları, masaüstü uygulamalarına yönelik istemci tarafında COM programlamayı kolaylaştırmak için kullanılabilir.

[#İmport Önişlemci yönergesini](../preprocessor/hash-import-directive-cpp.md)kullanarak, derleyici bir tür kitaplığını OKUYABILIR ve com arabirimlerini sınıflar olarak açıklayan bir C++ üstbilgi dosyasına dönüştürebilir. Oluşturulan tür kitaplığı `#import` üst bilgi dosyaları için içeriğin Kullanıcı denetimi için bir dizi öznitelik vardır.

Bir COM nesnesine bir genel benzersiz tanımlayıcı (GUID) atamak için [__declspec](../cpp/declspec.md) genişletilmiş öznitelik [UUID](../cpp/uuid-cpp.md) 'sini kullanabilirsiniz. [__Uuidof](../cpp/uuidof-operator.md) anahtar sözcüğü bir com NESNESIYLE ilişkili GUID 'yi ayıklamak için kullanılabilir. Başka bir **__declspec** özniteliği olan [özelliği](../cpp/property-cpp.md), bir com nesnesinin veri üyesi `get` için `set` ve yöntemlerini belirtmek için kullanılabilir.

`VARIANT` Ve `_com_raise_error`türlerini desteklemek, akıllı işaretçiler uygulamak ve tarafından oluşturulan hata nesnesini kapsüllemek için bir com desteği genel işlevleri ve sınıfları kümesi verilmiştir: `BSTR`

- [Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)

- [_bstr_t](../cpp/bstr-t-class.md)

- [_com_error](../cpp/com-error-class.md)

- [_com_ptr_t](../cpp/com-ptr-t-class.md)

- [_variant_t](../cpp/variant-t-class.md)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)<br/>
[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)
