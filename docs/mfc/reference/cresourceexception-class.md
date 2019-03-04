---
title: CResourceException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
ms.openlocfilehash: b29112b4901a1fecac37aa7ae61496e874959370
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268115"
---
# <a name="cresourceexception-class"></a>CResourceException sınıfı

Windows bulunamıyor veya istenen bir kaynağı ayırmak oluşturulur.

## <a name="syntax"></a>Sözdizimi

```
class CResourceException : public CSimpleException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CResourceException::CResourceException](#cresourceexception)|Oluşturur bir `CResourceException` nesne.|

## <a name="remarks"></a>Açıklamalar

Başka hiçbir nitelik gerekli veya mümkün değil.

Kullanma hakkında daha fazla bilgi için `CResourceException`, makaleye göz atın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CResourceException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cresourceexception"></a>  CResourceException::CResourceException

Oluşturur bir `CResourceException` nesne.

```
CResourceException();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu doğrudan kullanmaz, bunun yerine genel işlev çağrısı [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception). özel durumları hakkında daha fazla bilgi için bkz [MFC'de özel durum işleme](../exception-handling-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](cexception-class.md)<br/>
[Hiyerarşi Grafiği](../hierarchy-chart.md)
