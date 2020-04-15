---
title: CMemoryException Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
ms.openlocfilehash: 375b4227a25ae4c18cfd263eff4c3ec13f1304e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370001"
---
# <a name="cmemoryexception-class"></a>CMemoryException Sınıfı

Bellek dışı bir özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMemoryException : public CSimpleException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMemoryException::CMemoryException](#cmemoryexception)|Bir `CMemoryException` nesne inşa eder.|

## <a name="remarks"></a>Açıklamalar

Başka bir nitelik gerekli veya mümkün değildir. Bellek özel durumları **yeni**tarafından otomatik olarak atılır. `malloc`Örneğin, kendi bellek işlevlerinizi yazarsanız, bellek özel durumları atmanızdan siz sorumlusunuz.

Daha fazla `CMemoryException`bilgi için, [makaleözel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cexception](../../mfc/reference/cexception-class.md)

[Csimpleexception](../../mfc/reference/csimpleexception-class.md)

`CMemoryException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cmemoryexceptioncmemoryexception"></a><a name="cmemoryexception"></a>CMemoryException::CMemoryException

Bir `CMemoryException` nesne inşa eder.

```
CMemoryException();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuyu doğrudan kullanmayın, daha çok global işlevi [AfxThrowMemoryException'ı](exception-processing.md#afxthrowmemoryexception)arayın. bu genel işlev, daha önce ayrılmış bellekte özel durum nesnesi oluşturur, çünkü bellek dışı bir durumda başarılı olabilir. özel durum işleme hakkında daha fazla bilgi için makale [özel durumlarına](../exception-handling-in-mfc.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](cexception-class.md)<br/>
[Hiyerarşi Grafiği](../hierarchy-chart.md)
