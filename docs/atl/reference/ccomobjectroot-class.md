---
title: CComObjectRoot sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
dev_langs:
- C++
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2832b9866145d9af510302c8c6d327972205495
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38952974"
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot sınıfı
Bu tür tanımı, [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) iş parçacığı modeli sunucusunun varsayılan şablonlaştırılmış.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```  
  
## <a name="remarks"></a>Açıklamalar  
 `CComObjectRoot` olan bir `typedef` , [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) iş parçacığı modeli sunucusunun varsayılan şablonlaştırılmış. Bu nedenle [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) ya da başvuru [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).  
  
 `CComObjectRootEx` toplanmayan ve toplanan nesneler için nesne başvuru sayısı management işler. Nesnenizin değil toplanmakta olan ve nesnenizin toplanır, için dış bilinmeyen işaretçi tutan nesne başvuru sayısını tutar. Toplanan nesneler için `CComObjectRootEx` yöntemleri, iç nesneyi oluşturmak için hatasını işlemek için kullanılabilir ve iç nesne dış nesne iç arabirimleri yayımlandığında silinmeye karşı koru için silinir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComObjectRootEx sınıfı](../../atl/reference/ccomobjectrootex-class.md)   
 [CComAggObject sınıfı](../../atl/reference/ccomaggobject-class.md)   
 [CComObject sınıfı](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject sınıfı](../../atl/reference/ccompolyobject-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
