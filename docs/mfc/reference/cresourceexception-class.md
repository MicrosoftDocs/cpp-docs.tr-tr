---
description: 'Daha fazla bilgi edinin: CResourceException sınıfı'
title: CResourceException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
ms.openlocfilehash: c76635ae2cfa6c55bf54da7e73f6afbb44506fee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264875"
---
# <a name="cresourceexception-class"></a>CResourceException sınıfı

Windows istenen bir kaynağı bulamadığında veya ayıramadığında oluşturulur.

## <a name="syntax"></a>Syntax

```
class CResourceException : public CSimpleException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CResourceException:: CResourceException](#cresourceexception)|Bir `CResourceException` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Daha fazla nitelik gerekmez veya mümkün değildir.

Kullanma hakkında daha fazla bilgi için `CResourceException` bkz. [özel durum Işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CResourceException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cresourceexceptioncresourceexception"></a><a name="cresourceexception"></a> CResourceException:: CResourceException

Bir `CResourceException` nesnesi oluşturur.

```
CResourceException();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuyu doğrudan kullanmayın, ancak [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)genel işlevini çağırın. özel durumlar hakkında daha fazla bilgi için bkz. [MFC 'de özel durum işleme](../exception-handling-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[CException sınıfı](cexception-class.md)<br/>
[Hiyerarşi grafiği](../hierarchy-chart.md)
