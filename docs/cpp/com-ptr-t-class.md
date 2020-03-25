---
title: _com_ptr_t Sınıfı
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
ms.openlocfilehash: eeaab22ded537cbbb211a79596b8383251af3ab7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189916"
---
# <a name="_com_ptr_t-class"></a>_com_ptr_t Sınıfı

**Microsoft 'a özgü**

Bir **_com_ptr_t** NESNESI bir com arabirim işaretçisini kapsüller ve "Smart" işaretçisi olarak adlandırılır. Bu şablon sınıfı, `IUnknown` üye işlevlerine işlev çağrıları aracılığıyla kaynak ayırmayı ve ayırmayı yönetir: `QueryInterface`, `AddRef`ve `Release`.

Akıllı işaretçiye genellikle _COM_SMARTPTR_TYPEDEF makrosu tarafından verilen typedef tanımının başvurduğu. Bu makro bir arabirim adı ve IID alır ve arabirimin adı artı bir `Ptr`sonekini içeren **_com_ptr_t** bir özelleştirmesi bildirir. Örneğin:

```cpp
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
```

**_com_ptr_t** özelleştirme `IMyInterfacePtr`bildirir.

Bu şablon sınıfının üyesi olmayan bir dizi [işlev şablonu](../cpp/relational-function-templates.md), karşılaştırma işlecinin sağ tarafında bir akıllı işaretçiyle karşılaştırmaları destekler.

### <a name="construction"></a>İnşaat

|||
|-|-|
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|**_Com_ptr_t** nesnesi oluşturur.|

### <a name="low-level-operations"></a>Düşük düzey Işlemler

|||
|-|-|
|[AddRef](../cpp/com-ptr-t-addref.md)|Kapsüllenmiş arabirim İşaretçisinde `IUnknown` `AddRef` üye işlevini çağırır.|
|[Attach](../cpp/com-ptr-t-attach.md)|Bu akıllı işaretçinin türünün ham arabirim işaretçisini kapsüller.|
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|`CLSID` veya `ProgID`verilen bir nesnenin yeni bir örneğini oluşturur.|
|[Detach](../cpp/com-ptr-t-detach.md)|Kapsüllenmiş arabirim işaretçisini ayıklar ve döndürür.|
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|`CLSID` veya `ProgID`verilen bir nesnenin var olan örneğine iliştirir.|
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Kapsüllenmiş arabirim işaretçisini döndürür.|
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Kapsüllenmiş arabirim İşaretçisinde `IUnknown` `QueryInterface` üye işlevini çağırır.|
|[Sürüm](../cpp/com-ptr-t-release.md)|Kapsüllenmiş arabirim İşaretçisinde `IUnknown` `Release` üye işlevini çağırır.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](../cpp/com-ptr-t-operator-equal.md)|Varolan bir **_com_ptr_t** nesnesine yeni bir değer atar.|
|[işleçler = =,! =, \<, >, \<=, > =](../cpp/com-ptr-t-relational-operators.md)|Akıllı işaretçi nesnesini başka bir akıllı işaretçi, ham arabirim işaretçisi veya NULL ile karşılaştırın.|
|[Ayıklayıcıları](../cpp/com-ptr-t-extractors.md)|Kapsüllenmiş COM arabirimi işaretçisini ayıklayın.|

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<comıp. h >

**Lib:** comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)
