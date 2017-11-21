---
title: "CComEnum sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
dev_langs: C++
helpviewer_keywords: CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 417dcf3ff0d578c4febcefb5caa6989ed98bb209
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomenum-class"></a>CComEnum sınıfı
Bu sınıf bir dizisine göre bir COM Numaralandırıcı nesnesi tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class ThreadModel = CcomObjectThreadModel>  
class ATL_NO_VTABLE CComEnum : public CComEnumImpl<Base, piid,
 T,
    Copy>,
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
 Bir homojen [kopyalama ilke sınıfı](../../atl/atl-copy-policy-classes.md).  
  
 `ThreadModel`  
 Sınıfın iş parçacığı modeli. Bu parametre projenizde kullanılan genel nesne iş parçacığı modelini varsayılan olarak ayarlanır.  
  
## <a name="remarks"></a>Açıklamalar  
 `CComEnum`bir dizisine göre bir COM Numaralandırıcı nesnesi tanımlar. Bu sınıf için paraleldir [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) bir C++ Standart Kitaplığı kapsayıcı dayalı bir numaralandırıcı uygular. Bu sınıf kullanma için tipik adımları aşağıda özetlenmiştir. Daha fazla bilgi için bkz: [ATL koleksiyonları ve numaralandırmalar](../../atl/atl-collections-and-enumerators.md).  
  
## <a name="to-use-this-class"></a>Bu sınıf kullanmak için:  
  
- `typedef`Bu sınıf uzmanlaşması.  
  
-   Kullanım `typedef` bir alt uzmanlaşması şablon bağımsız değişken olarak `CComObject`.  
  
-   Bir örneğini oluşturmak `CComObject` uzmanlık.  
  
-   Numaralandırıcı nesnesi çağırarak başlatılmaya [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init).  
  
-   Numaralandırıcı arabirimi istemciye döndür.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CComObjectRootBase`  
  
 `Base`  
  
 [İn uygulamasına](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
## <a name="example"></a>Örnek  
 Aşağıda gösterilen kodu oluşturma ve bir Numaralayıcı nesnesi başlatılırken yeniden kullanılabilir bir işlev sağlar.  
  
 [!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]  
  
 Bu şablon işlevi uygulamak için kullanılan `_NewEnum` aşağıda gösterildiği gibi bir koleksiyon arabiriminin özelliği:  
  
 [!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]  
  
 Bu kod oluşturur bir `typedef` için `CComEnum` bir vektör sunan **değişken**aracılığıyla s **IEnumVariant** arabirimi. **CVariantArrayCollection** sınıfı yalnızca uzmanlaşmış **CreateEnumerator** bu tür ve geçişleri gerekli bağımsız değişkenleri Numaralandırıcı nesneleriyle çalışmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [CComEnumImpl sınıfı](../../atl/reference/ccomenumimpl-class.md)   
 [İn uygulamasına sınıfı](../../atl/reference/ccomobjectrootex-class.md)
