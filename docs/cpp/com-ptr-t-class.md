---
title: _com_ptr_t sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t
dev_langs:
- C++
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb343431a52df9fae32bb17f3303738c04385cf5
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948026"
---
# <a name="comptrt-class"></a>_com_ptr_t Sınıfı
**Microsoft'a özgü**  
  
 A `_com_ptr_t` nesne bir COM arabirimi işaretçisini kapsüller ve "Akıllı" bir işaretçi olarak adlandırılır. Bu şablon sınıfının kaynak ayırmayı ve ayırmayı kaldırma işlev çağrılarıyla yönetir `IUnknown` üye işlevleri: `QueryInterface`, `AddRef`, ve `Release`.  
  
 Akıllı bir işaretçi, genellikle _COM_SMARTPTR_TYPEDEF makro tarafından sağlanan typedef tanımı tarafından başvuruluyor. Bu makro bir arabirim adı ve IID alır ve bir alt uzmanlaşması bildirir `_com_ptr_t` arabirimi yanı sıra son eki adıyla `Ptr`. Örneğin:  
  
```cpp 
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 bildirir `_com_ptr_t` özelleştirmesi `IMyInterfacePtr`.  
  
 Bir dizi [işlev şablonları](../cpp/relational-function-templates.md), bu şablon üyeleri sınıf, akıllı bir işaretçi karşılaştırma işlecinin sağ tarafında destek karşılaştırmalar.  
  
### <a name="construction"></a>Oluşturma  
  
|||  
|-|-|  
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|Oluşturur bir `_com_ptr_t` nesne.|  
  
### <a name="low-level-operations"></a>Düşük düzey işlemler  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|Çağrıları `AddRef` üye işlevinin `IUnknown` kapsüllenmiş arabirim işaretçisini üzerinde.|  
|[Attach](../cpp/com-ptr-t-attach.md)|Bu akıllı işaretçinin türü ham arabirim işaretçisi kapsüller.|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Verilen nesne yeni bir örneğini oluşturur bir `CLSID` veya `ProgID`.|  
|[Detach](../cpp/com-ptr-t-detach.md)|Kapsüllenmiş arabirim işaretçisini ayıklar ve döndürür.|  
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|Verilen bir nesnenin varolan örneğine için bir `CLSID` veya `ProgID`.|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Kapsüllenmiş arabirim işaretçisini döndürür.|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Çağrıları `QueryInterface` üye işlevinin `IUnknown` kapsüllenmiş arabirim işaretçisini üzerinde.|  
|[Sürüm](../cpp/com-ptr-t-release.md)|Çağrıları `Release` üye işlevinin `IUnknown` kapsüllenmiş arabirim işaretçisini üzerinde.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](../cpp/com-ptr-t-operator-equal.md)|Mevcut bir yeni bir değer atar `_com_ptr_t` nesne.|  
|[işleçler ==,! =, \<, >, \<=, > =](../cpp/com-ptr-t-relational-operators.md)|NULL veya başka bir akıllı işaretçinin, ham arabirim işaretçisi için akıllı işaretçi nesnesinin karşılaştırın.|  
|[Ayıklayıcıları](../cpp/com-ptr-t-extractors.md)|Kapsüllenmiş COM arabirimi işaretçisini ayıklayın.|  
  
**END Microsoft özgü**  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<comip.h >  
  
 **Lib:** comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel türü olduğu)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)