---
title: CComObjectRoot Class
ms.date: 11/04/2016
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
ms.openlocfilehash: 9a9ffa1813fb15297d209894050b6bcce6802df2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298652"
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot Class

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

## <a name="see-also"></a>Ayrıca bkz.

[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComAggObject Sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject Sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject Sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
