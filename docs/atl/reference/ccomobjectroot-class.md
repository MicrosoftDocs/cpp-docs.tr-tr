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
ms.openlocfilehash: e6a7d350f7bd50476c1c327d824089981d3e8321
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359038"
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot sınıfı
Bu typedef, [in uygulamasına](../../atl/reference/ccomobjectrootex-class.md) iş parçacığı modeli sunucusunun varsayılan şablonlaştırılmış.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```  
  
## <a name="remarks"></a>Açıklamalar  
 `CComObjectRoot` olan bir `typedef` , [in uygulamasına](../../atl/reference/ccomobjectrootex-class.md) iş parçacığı modeli sunucusunun varsayılan şablonlaştırılmış. Bu nedenle [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) ya da başvurur [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).  
  
 `CComObjectRootEx` Nesne başvuru sayısı Yönetimi toplanmayan ve toplanan nesneler için işler. Nesnenizin değil toplanmakta ve nesnenizin toplanır varsa işaretçinin dış bilinmeyen tutan nesne başvurusu sayısı tutar. Toplanan nesneler için `CComObjectRootEx` yöntemleri oluşturmak için iç nesneyi başarısızlığını işlemek için kullanılabilir ve dış iç arabirimleri yayımlandığında silinmeye karşı veya iç nesneyi korumak için silinir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İn uygulamasına sınıf üyeleri](http://msdn.microsoft.com/en-us/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [İn uygulamasına sınıfı](../../atl/reference/ccomobjectrootex-class.md)   
 [CComAggObject sınıfı](../../atl/reference/ccomaggobject-class.md)   
 [CComObject sınıfı](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject sınıfı](../../atl/reference/ccompolyobject-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
