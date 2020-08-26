---
title: _com_ptr_t Sınıfı
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
ms.openlocfilehash: 2c299ea4a5aaabba847c85500a6023d7b112d492
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838509"
---
# <a name="_com_ptr_t-class"></a>_com_ptr_t Sınıfı

**Microsoft'a Özgü**

Bir **_com_ptr_t** NESNESI bir com arabirim işaretçisini kapsüller ve "Smart" işaretçisi olarak adlandırılır. Bu şablon sınıfı, üye işlevlerine işlev çağrıları aracılığıyla kaynak ayırmayı ve ayırmayı yönetir `IUnknown` : `QueryInterface` , `AddRef` ve `Release` .

Akıllı işaretçiye genellikle _COM_SMARTPTR_TYPEDEF makrosu tarafından verilen typedef tanımının başvurduğu. Bu makro bir arabirim adı ve IID alır ve bir **_com_ptr_t** özelleştirmeyi, arabirimin adı artı bir soneki olarak bildirir `Ptr` . Örnek:

```cpp
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
```

**_com_ptr_t** özelleştirmesi bildirir `IMyInterfacePtr` .

Bu şablon sınıfının üyesi olmayan bir dizi [işlev şablonu](../cpp/relational-function-templates.md), karşılaştırma işlecinin sağ tarafında bir akıllı işaretçiyle karşılaştırmaları destekler.

### <a name="construction"></a>İnşaat

| Ad | Açıklama |
|-|-|
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|**_Com_ptr_t** nesnesi oluşturur.|

### <a name="low-level-operations"></a>Düşük düzey Işlemler

| Ad | Açıklama |
|-|-|
|[AddRef](../cpp/com-ptr-t-addref.md)|`AddRef` `IUnknown` Kapsüllenmiş arabirim İşaretçisinde öğesinin üye işlevini çağırır.|
|[İliştir](../cpp/com-ptr-t-attach.md)|Bu akıllı işaretçinin türünün ham arabirim işaretçisini kapsüller.|
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Veya verilen bir nesnenin yeni bir örneğini oluşturur `CLSID` `ProgID` .|
|[Ayır](../cpp/com-ptr-t-detach.md)|Kapsüllenmiş arabirim işaretçisini ayıklar ve döndürür.|
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|Veya verilen bir nesnenin var olan örneğine iliştirir `CLSID` `ProgID` .|
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Kapsüllenmiş arabirim işaretçisini döndürür.|
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|`QueryInterface` `IUnknown` Kapsüllenmiş arabirim İşaretçisinde öğesinin üye işlevini çağırır.|
|[Sürüm](../cpp/com-ptr-t-release.md)|`Release` `IUnknown` Kapsüllenmiş arabirim İşaretçisinde öğesinin üye işlevini çağırır.|

### <a name="operators"></a>İşleçler

| Ad | Açıklama |
|-|-|
|[işleç =](../cpp/com-ptr-t-operator-equal.md)|Varolan bir **_com_ptr_t** nesnesine yeni bir değer atar.|
|[işleçler = =,! =, \<, > , \<=, >=](../cpp/com-ptr-t-relational-operators.md)|Akıllı işaretçi nesnesini başka bir akıllı işaretçi, ham arabirim işaretçisi veya NULL ile karşılaştırın.|
|[Ayıklayıcıları](../cpp/com-ptr-t-extractors.md)|Kapsüllenmiş COM arabirimi işaretçisini ayıklayın.|

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<comip.h>

**Lib:** comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM desteği sınıfları](../cpp/compiler-com-support-classes.md)
