---
title: CResourceException Sınıf
ms.date: 11/04/2016
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
ms.openlocfilehash: 557bfe1cc41c3dda65bd95d7d687820c0b9862b7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368323"
---
# <a name="cresourceexception-class"></a>CResourceException Sınıf

Windows istenen bir kaynağı bulamıyorsa veya ayıramıyorsa oluşturulur.

## <a name="syntax"></a>Sözdizimi

```
class CResourceException : public CSimpleException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CResourceException::CResourceException](#cresourceexception)|Bir `CResourceException` nesne inşa eder.|

## <a name="remarks"></a>Açıklamalar

Başka bir nitelik gerekli veya mümkün değildir.

Kullanma `CResourceException`hakkında daha fazla bilgi için, özel [durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cexception](../../mfc/reference/cexception-class.md)

[Csimpleexception](../../mfc/reference/csimpleexception-class.md)

`CResourceException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cresourceexceptioncresourceexception"></a><a name="cresourceexception"></a>CResourceException::CResourceException

Bir `CResourceException` nesne inşa eder.

```
CResourceException();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuyu doğrudan kullanmayın, daha çok global işlevi [AfxThrowResourceException'ı](exception-processing.md#afxthrowresourceexception)arayın. özel durumlar hakkında daha fazla bilgi için [MFC'deki Özel Durum İşleme makalesine](../exception-handling-in-mfc.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](cexception-class.md)<br/>
[Hiyerarşi Grafiği](../hierarchy-chart.md)
