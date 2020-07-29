---
title: CComObjectRoot sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
ms.openlocfilehash: 98868e67fd14899a75f86837034ba540d22039e3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224246"
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot sınıfı

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) Bu typedef, sunucunun varsayılan iş parçacığı modelinde şablonsaldır.

## <a name="syntax"></a>Sözdizimi

```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```

## <a name="remarks"></a>Açıklamalar

`CComObjectRoot`, **`typedef`** sunucunun varsayılan iş parçacığı modelinde [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) şablonsaldır. Böylece [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) , [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) veya [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md)'e başvurur.

`CComObjectRootEx`hem toplanmış hem de toplanmış nesneler için nesne başvuru sayısı yönetimini işler. Nesneniz toplanmıyor ise nesne başvuru sayısını tutar ve nesneniz toplanırsa bu, bilinmeyen dış öğesine işaretçiyi barındırır. Toplanmış nesneler için `CComObjectRootEx` Yöntemler, oluşturulacak iç nesnenin başarısızlığını işlemek ve iç arabirimler serbest bırakıldığında ya da iç nesne silindiğinde, dış nesne silinmeye karşı korumak için kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="see-also"></a>Ayrıca bkz.

[CComObjectRootEx sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComAggObject sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
