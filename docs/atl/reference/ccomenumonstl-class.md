---
title: CComEnumOnSTL sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
dev_langs:
- C++
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca7b7d38c204d7dd8402b9d610a5800dcef6ced9
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883235"
---
# <a name="ccomenumonstl-class"></a>CComEnumOnSTL sınıfı
Bu sınıf, bir C++ Standart Kitaplığı koleksiyonuna bağlı bir COM Numaralandırıcı nesnesi tanımlar.  
  
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
 *temel*  
 Bir COM Numaralandırıcı ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) arabirimi.  
  
 *piid*  
 Numaralandırıcı arabirimi arabirim kimliği için bir işaretçi.  
  
 *T*  
 Numaralandırıcı arabirim tarafından sunulan öğe türü.  
  
 *kopyalama*  
 A [kopyalama İlkesi](../../atl/atl-copy-policy-classes.md) sınıfı.  
  
 *CollType*  
 Bir C++ Standart Kitaplığı kapsayıcı sınıfı.  
  
## <a name="remarks"></a>Açıklamalar  
 `CComEnumOnSTL` bir C++ Standart Kitaplığı koleksiyonuna bağlı bir COM Numaralandırıcı nesnesi tanımlar. Bu sınıf kendi veya o ilkelerle birlikte kullanılabilir [Icollectiononstlımpl](../../atl/reference/icollectiononstlimpl-class.md). Bu sınıf kullanmak için tipik adımları aşağıda özetlenmiştir. Daha fazla bilgi için [ATL koleksiyonları ve numaralandırıcıları](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class-with-icollectiononstlimpl"></a>Bu sınıf Icollectiononstlımpl ile kullanmak için:  
  
- **TypeDef** bu sınıfın özelleştirmesi.  
  
-   Kullanım **typedef** özelleştirmesi son şablon bağımsız değişken olarak `ICollectionOnSTLImpl`.  
  
 Bkz: [ATL koleksiyonları ve numaralandırıcıları](../../atl/atl-collections-and-enumerators.md) örneği.  
  
## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>Bu sınıf Icollectiononstlımpl bağımsız olarak kullanmak için:  
  
- **TypeDef** bu sınıfın özelleştirmesi.  
  
-   Kullanım **typedef** özelleştirmesi şablon bağımsız değişken olarak `CComObject`.  
  
-   Bir örneğini oluşturmak `CComObject` özelleştirmesi.  
  
-   Numaralandırıcı nesnesi çağırarak denetlediği başlatmak [IEnumOnSTLImpl::Init](../../atl/reference/ienumonstlimpl-class.md#init).  
  
-   Numaralandırıcı arabirimi istemciye döndürür.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [Ienumonstlımpl](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
## <a name="example"></a>Örnek  
 Aşağıda gösterilen kod oluşturulması ve başlatılması bir sabit listesi nesnesi işlemek için genel bir işlev sağlar:  
  
 [!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]  
  
 Bu şablon işlevi uygulamak için kullanılan `_NewEnum` aşağıda gösterildiği gibi bir toplama arabirimin özelliği:  
  
 [!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]  
  
 Bu kod oluşturur bir **typedef** için `CComEnumOnSTL` oluşan bir vektörü sunan `CComVariant`s yoluyla `IEnumVariant` arabirimi. `CVariantCollection` Sınıfı yalnızca uzmanlaşmış `CreateSTLEnumerator` Numaralandırıcı bu tür nesnelerle çalışmayı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ienumonstlımpl](../../atl/reference/ienumonstlimpl-class.md)   
 [ATLCollections örnek: Icollectiononstlımpl ve CComEnumOnSTL özel kopyalama İlkesi sınıfları gösterir](../../visual-cpp-samples.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)   
 [CComObjectRootEx sınıfı](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [IEnumOnSTLImpl Sınıfı](../../atl/reference/ienumonstlimpl-class.md)
