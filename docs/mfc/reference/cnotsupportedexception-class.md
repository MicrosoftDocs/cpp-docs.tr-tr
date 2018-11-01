---
title: CNotSupportedException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
ms.openlocfilehash: 0eb3bf0de51345ed4316d2a1c5c29b8ecb3e8bba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456569"
---
# <a name="cnotsupportedexception-class"></a>CNotSupportedException sınıfı

Desteklenmeyen bir özellik isteğinden kaynaklanan bir özel durum temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CNotSupportedException : public CSimpleException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|Oluşturur bir `CNotSupportedException` nesne.|

## <a name="remarks"></a>Açıklamalar

Başka hiçbir nitelik gerekli veya mümkün değil.

Kullanma hakkında daha fazla bilgi için `CNotSupportedException`, makaleye göz atın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CNotSupportedException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="cnotsupportedexception"></a>  CNotSupportedException::CNotSupportedException

Oluşturur bir `CNotSupportedException` nesne.

```
CNotSupportedException();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu doğrudan kullanmaz, bunun yerine genel işlev çağrısı [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception). özel durum işleme hakkında daha fazla bilgi için bkz [MFC'de özel durum işleme](../exception-handling-in-mfc.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CException Sınıfı](cexception-class.md)<br/>
[Hiyerarşi Grafiği](../hierarchy-chart.md)

