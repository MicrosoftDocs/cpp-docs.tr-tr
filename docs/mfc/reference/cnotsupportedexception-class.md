---
description: 'Daha fazla bilgi edinin: CNotSupportedException sınıfı'
title: CNotSupportedException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
ms.openlocfilehash: 61bf729753897e1d30c5a12bc371489ba6f2d64f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331484"
---
# <a name="cnotsupportedexception-class"></a>CNotSupportedException sınıfı

Desteklenmeyen bir özellik için isteğin sonucu olan bir özel durumu temsil eder.

## <a name="syntax"></a>Syntax

```
class CNotSupportedException : public CSimpleException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CNotSupportedException:: CNotSupportedException](#cnotsupportedexception)|Bir `CNotSupportedException` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Daha fazla nitelik gerekmez veya mümkün değildir.

Kullanma hakkında daha fazla bilgi için `CNotSupportedException` bkz. [özel durum Işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CNotSupportedException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="cnotsupportedexceptioncnotsupportedexception"></a><a name="cnotsupportedexception"></a> CNotSupportedException:: CNotSupportedException

Bir `CNotSupportedException` nesnesi oluşturur.

```
CNotSupportedException();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuyu doğrudan kullanmayın, ancak [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception)genel işlevini çağırın. özel durum işleme hakkında daha fazla bilgi için bkz. [MFC 'de özel durum işleme](../exception-handling-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[CException sınıfı](cexception-class.md)<br/>
[Hiyerarşi grafiği](../hierarchy-chart.md)
