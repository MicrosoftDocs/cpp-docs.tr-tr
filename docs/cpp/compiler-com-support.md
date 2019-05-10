---
title: Derleyici COM Desteği
ms.date: 05/06/2019
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 76a78442-f2a4-4985-9967-67e20773f847
ms.openlocfilehash: e13874bad44610821bed9c588af6bd9124162116
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222214"
---
# <a name="compiler-com-support"></a>Derleyici COM Desteği

## <a name="microsoft-specific"></a>Microsoft'a Özgü

Microsoft C++ derleyici, doğrudan Bileşen Nesne Modeli (COM) tür kitaplıkları'nı okuyun ve içeriği çevirme C++ kaynak derlemeye dahil kodu. Dil uzantıları, istemci tarafında programlama COM kolaylaştırmak kullanılabilir.

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