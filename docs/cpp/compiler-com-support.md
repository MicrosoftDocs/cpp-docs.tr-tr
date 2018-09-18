---
title: Derleyici COM desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: faab8e0dafdf9121ab694c409500c08aabbb1bc8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079745"
---
# <a name="compiler-com-support"></a>Derleyici COM Desteği

## <a name="microsoft-specific"></a>Microsoft'a Özgü

Visual C++ derleyicisi, doğrudan Bileşen Nesne Modeli (COM) tür kitaplıkları'nı okuyun ve derlemeye dahil C++ kaynak koda içeriği çevirir. Dil uzantıları, istemci tarafında programlama COM kolaylaştırmak kullanılabilir.

Kullanarak [#import önişlemci yönergesi](../preprocessor/hash-import-directive-cpp.md), derleyici bir tür kitaplığı okuyabilir ve COM tanımlayan bir C++ üstbilgi dosyası içine arabirimleri olarak dönüştürme sınıfları. Bir dizi `#import` öznitelikleri, kullanıcı denetimi elde edilen tür kitaplığı üstbilgi dosyaları içeriğin kullanılabilir.

Kullanabileceğiniz [__declspec](../cpp/declspec.md) genişletilmiş öznitelik [UUID](../cpp/uuid-cpp.md) bir COM nesnesi için bir genel benzersiz tanıtıcısı (GUID) atanamıyor. Anahtar sözcüğü [__uuidof](../cpp/uuidof-operator.md) bir COM nesnesi ile ilişkili GUID'sini ayıklamak için kullanılabilir. Başka bir **__declspec** özniteliği [özelliği](../cpp/property-cpp.md), belirtmek için kullanılan `get` ve `set` bir COM nesnesi veri üyesi için yöntemleri.

COM desteği genel işlevleri ve sınıfları kümesi desteklemek için sağlanan `VARIANT` ve `BSTR` türleri, akıllı işaretçiler uygulamak ve tarafından oluşturulan hata nesnesi kapsülleyen `_com_raise_error`:

- [Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)

- [_bstr_t](../cpp/bstr-t-class.md)

- [_com_error](../cpp/com-error-class.md)

- [_com_ptr_t](../cpp/com-ptr-t-class.md)

- [_variant_t](../cpp/variant-t-class.md)

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)<br/>
[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)