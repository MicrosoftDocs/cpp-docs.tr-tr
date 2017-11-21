---
title: "CComEnumOnSTL sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
dev_langs: C++
helpviewer_keywords: CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 740d1d35781fcea7820bfcb32171b744534b20fe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomenumonstl-class"></a>CComEnumOnSTL sınıfı
Bu sınıf bir C++ Standart Kitaplığı koleksiyona bağlı bir COM Numaralandırıcı nesnesi tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class CollType, class ThreadModel = CComObjectThreadModel>  
class ATL_NO_VTABLE CComEnumOnSTL : public IEnumOnSTLImpl<Base, piid,
 T,
    Copy,
 CollType>,
    public CComObjectRootEx<ThreadModel>
```  
  
#### <a name="parameters"></a>Parametreler  
 `Base`  
 Bir COM Numaralandırıcı ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) arabirimi.  
  
 `piid`  
 Numaralandırıcı arabirimi arabirim kimliği için bir işaretçi.  
  
 `T`  
 Numaralandırıcı arabirimi tarafından gösterilen öğenin türü.  
  
 `Copy`  
 A [kopyalama İlkesi](../../atl/atl-copy-policy-classes.md) sınıfı.  
  
 `CollType`  
 C++ Standart Kitaplığı kapsayıcı sınıfı.  
  
## <a name="remarks"></a>Açıklamalar  
 `CComEnumOnSTL`bir C++ Standart Kitaplığı koleksiyona bağlı bir COM Numaralandırıcı nesnesi tanımlar. Bu sınıf kendi başına veya birlikte kullanılan [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md). Bu sınıf kullanma için tipik adımları aşağıda özetlenmiştir. Daha fazla bilgi için bkz: [ATL koleksiyonları ve numaralandırmalar](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class-with-icollectiononstlimpl"></a>Bu sınıf ICollectionOnSTLImpl ile kullanmak için:  
  
- `typedef`Bu sınıf uzmanlaşması.  
  
-   Kullanım `typedef` bir alt uzmanlaşması son şablon bağımsız değişken olarak `ICollectionOnSTLImpl`.  
  
 Bkz: [ATL koleksiyonları ve numaralandırmalar](../../atl/atl-collections-and-enumerators.md) bir örnek.  
  
## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>Bu sınıf ICollectionOnSTLImpl bağımsız olarak kullanmak için:  
  
- `typedef`Bu sınıf uzmanlaşması.  
  
-   Kullanım `typedef` bir alt uzmanlaşması şablon bağımsız değişken olarak `CComObject`.  
  
-   Bir örneğini oluşturmak `CComObject` uzmanlık.  
  
-   Numaralandırıcı nesnesi çağırarak başlatılmaya [IEnumOnSTLImpl::Init](../../atl/reference/ienumonstlimpl-class.md#init).  
  
-   Numaralandırıcı arabirimi istemciye döndür.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CComObjectRootBase`  
  
 `Base`  
  
 [İn uygulamasına](../../atl/reference/ccomobjectrootex-class.md)  
  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
## <a name="example"></a>Örnek  
 Aşağıda gösterilen kodu oluşturma ve başlatma Numaralandırıcı nesnenin işlemek için genel bir işlev sağlar:  
  
 [!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]  
  
 Bu şablon işlevi uygulamak için kullanılan `_NewEnum` aşağıda gösterildiği gibi bir koleksiyon arabiriminin özelliği:  
  
 [!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]  
  
 Bu kod oluşturur bir `typedef` için `CComEnumOnSTL` bir vektör sunan `CComVariant`yoluyla s **IEnumVariant** arabirimi. **CVariantCollection** sınıfı yalnızca uzmanlaşmış **CreateSTLEnumerator** Numaralandırıcı nesne türü ile çalışmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)   
 [ATLCollections örnek: ICollectionOnSTLImpl, CComEnumOnSTL ve özel kopyalama İlkesi sınıfları gösterir](../../visual-cpp-samples.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [İn uygulamasına sınıfı](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [IEnumOnSTLImpl sınıfı](../../atl/reference/ienumonstlimpl-class.md)
