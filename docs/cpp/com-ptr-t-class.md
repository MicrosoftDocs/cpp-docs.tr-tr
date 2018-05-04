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
ms.openlocfilehash: 8ec54735fce39cc54bdb5e396da7c637b889b92c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="comptrt-class"></a>_com_ptr_t Sınıfı
**Microsoft özel**  
  
 A `_com_ptr_t` nesne COM arabirimi işaretçisi yalıtır ve "Akıllı" bir işaretçi olarak adlandırılır. Bu şablon sınıfı kaynak ayırma ve ayırmayı kaldırma işlev çağrılarını aracılığıyla yönetir **IUnknown** üye işlevleri: `QueryInterface`, `AddRef`, ve **sürüm**.  
  
 Akıllı bir işaretçi genellikle tarafından sağlanan typedef tanımı tarafından başvurulan **_COM_SMARTPTR_TYPEDEF** makrosu. Bu makrosu bir arabirim adı ve IID alır ve bir alt uzmanlaşması bildirir `_com_ptr_t` arabirimi artı sonekine adıyla `Ptr`. Örneğin:  
  
```  
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 bildirir `_com_ptr_t` uzmanlık **IMyInterfacePtr**.  
  
 Bir dizi [işlev şablonları](../cpp/relational-function-templates.md), bu şablonu üyesi değilse sınıfı, destek karşılaştırmaları karşılaştırma işlecinin sağ tarafında akıllı işaretçiyle.  
  
### <a name="construction"></a>Yapı  
  
|||  
|-|-|  
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|Oluşturan bir `_com_ptr_t` nesnesi.|  
  
### <a name="low-level-operations"></a>Düşük düzey işlemler  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|Çağrıları `AddRef` üye işlevini **IUnknown** kapsüllenmiş arabirim işaretçisi üzerinde.|  
|[Attach](../cpp/com-ptr-t-attach.md)|Bu akıllı işaretçinin türü ham arabirim işaretçisi yalıtır.|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Verilen bir nesne yeni bir örneğini oluşturur bir **CLSID** veya **ProgID**.|  
|[Detach](../cpp/com-ptr-t-detach.md)|Kapsüllenmiş arabirim işaretçisini ayıklar ve döndürür.|  
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|Varolan bir nesneyi, verilen örneğine bağlanan bir **CLSID** veya **ProgID**.|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Kapsüllenmiş arabirim işaretçisi döndürür.|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Çağrıları `QueryInterface` üye işlevini **IUnknown** kapsüllenmiş arabirim işaretçisi üzerinde.|  
|[Sürüm](../cpp/com-ptr-t-release.md)|Çağrıları **sürüm** üye işlevini **IUnknown** kapsüllenmiş arabirim işaretçisi üzerinde.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](../cpp/com-ptr-t-operator-equal.md)|Var olan yeni bir değer atar `_com_ptr_t` nesnesi.|  
|[işleç ==,! =, \<, >, \<=, > =](../cpp/com-ptr-t-relational-operators.md)|Başka bir akıllı işaretçi, ham arabirim işaretçisi akıllı işaretçi nesnesine karşılaştırmak veya **NULL**.|  
|[Ayıklayıcıları](../cpp/com-ptr-t-extractors.md)|Kapsüllenmiş COM arabirimi işaretçisini ayıklayın.|  
  
**SON Microsoft özel**  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<comip.h >  
  
 **LIB:** comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel tür olan)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)