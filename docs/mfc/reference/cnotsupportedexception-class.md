---
title: CNotSupportedException Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
ms.openlocfilehash: b859b939baef018e69b245e597eea90e608253ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363190"
---
# <a name="cnotsupportedexception-class"></a>CNotSupportedException Sınıfı

Desteklenmeyen bir özellik için istek sonucu bir özel durum temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CNotSupportedException : public CSimpleException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|Bir `CNotSupportedException` nesne inşa eder.|

## <a name="remarks"></a>Açıklamalar

Başka bir nitelik gerekli veya mümkün değildir.

Kullanma `CNotSupportedException`hakkında daha fazla bilgi için, özel [durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cexception](../../mfc/reference/cexception-class.md)

[Csimpleexception](../../mfc/reference/csimpleexception-class.md)

`CNotSupportedException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cnotsupportedexceptioncnotsupportedexception"></a><a name="cnotsupportedexception"></a>CNotSupportedException::CNotSupportedException

Bir `CNotSupportedException` nesne inşa eder.

```
CNotSupportedException();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuyu doğrudan kullanmayın, daha çok global işlevi [AfxThrowNotSupportedException'ı](exception-processing.md#afxthrownotsupportedexception)arayın. özel durum işleme hakkında daha fazla bilgi için [MFC'deki Özel Durum İşleme makalesine](../exception-handling-in-mfc.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](cexception-class.md)<br/>
[Hiyerarşi Grafiği](../hierarchy-chart.md)
