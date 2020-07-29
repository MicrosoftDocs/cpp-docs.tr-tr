---
title: Derleyici COM Desteği
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
ms.openlocfilehash: 9a5961049cbc54c94cec5b444e2d98f013dda932
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233788"
---
# <a name="compiler-com-support"></a>Derleyici COM Desteği

**Microsoft'a Özgü**

Microsoft C++ derleyicisi, bileşen nesne modeli (COM) tür kitaplıklarını doğrudan okuyabilir ve içeriği derlemeye dahil edilebilir C++ kaynak koduna çevirebilir. Dil uzantıları, masaüstü uygulamalarına yönelik istemci tarafında COM programlamayı kolaylaştırmak için kullanılabilir.

[#İmport Önişlemci yönergesini](../preprocessor/hash-import-directive-cpp.md)kullanarak, derleyici bir tür kitaplığını OKUYABILIR ve com arabirimlerini sınıflar olarak açıklayan bir C++ üst bilgi dosyasına dönüştürebilir. `#import`Oluşturulan tür kitaplığı üst bilgi dosyaları için içeriğin Kullanıcı denetimi için bir dizi öznitelik vardır.

Bir COM nesnesine bir genel benzersiz tanımlayıcı (GUID) atamak için [__declspec](../cpp/declspec.md) genişletilmiş öznitelik [UUID](../cpp/uuid-cpp.md) 'sini kullanabilirsiniz. Anahtar sözcüğü [__uuidof](../cpp/uuidof-operator.md) bir com NESNESIYLE ilişkili GUID 'yi ayıklamak için kullanılabilir. Bir **`__declspec`** [property](../cpp/property-cpp.md) `get` `set` com nesnesinin veri üyesi için ve yöntemlerini belirtmek için başka bir öznitelik, özelliği kullanılabilir.

`VARIANT`Ve `BSTR` türlerini desteklemek, akıllı işaretçiler uygulamak ve tarafından oluşturulan hata nesnesini kapsüllemek IÇIN bir com desteği genel işlevleri ve sınıfları kümesi verilmiştir `_com_raise_error` :

- [Derleyici COM genel Işlevleri](../cpp/compiler-com-global-functions.md)

- [_bstr_t](../cpp/bstr-t-class.md)

- [_com_error](../cpp/com-error-class.md)

- [_com_ptr_t](../cpp/com-ptr-t-class.md)

- [_variant_t](../cpp/variant-t-class.md)

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM desteği sınıfları](../cpp/compiler-com-support-classes.md)<br/>
[Derleyici COM genel Işlevleri](../cpp/compiler-com-global-functions.md)
