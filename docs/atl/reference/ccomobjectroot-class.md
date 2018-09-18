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
ms.openlocfilehash: 2647ea3ac46ec3783f584de996c3d988c168980d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054869"
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

[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComAggObject Sınıfı](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject Sınıfı](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject Sınıfı](../../atl/reference/ccompolyobject-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
