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
ms.openlocfilehash: c3af508cd39e277ca4ae0a9aad5e639f66edc53b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294817"
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

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](cexception-class.md)<br/>
[Hiyerarşi Grafiği](../hierarchy-chart.md)
