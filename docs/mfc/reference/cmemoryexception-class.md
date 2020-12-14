---
description: 'Daha fazla bilgi edinin: CMemoryException sınıfı'
title: CMemoryException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
ms.openlocfilehash: 694629d65c8b4cffc351873d5da3d8ed3c34cf8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336653"
---
# <a name="cmemoryexception-class"></a>CMemoryException sınıfı

Bellek dışı özel durum koşulunu temsil eder.

## <a name="syntax"></a>Syntax

```
class CMemoryException : public CSimpleException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMemoryException:: CMemoryException](#cmemoryexception)|Bir `CMemoryException` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Daha fazla nitelik gerekmez veya mümkün değildir. Bellek özel durumları tarafından otomatik olarak oluşturulur **`new`** . Örneğin, kullanarak kendi bellek işlevlerinizi yazarsanız, `malloc` bellek özel durumlarını oluşturmaktan sorumlu olursunuz.

Hakkında daha fazla bilgi için `CMemoryException` bkz. [özel durum Işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CMemoryException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="cmemoryexceptioncmemoryexception"></a><a name="cmemoryexception"></a> CMemoryException:: CMemoryException

Bir `CMemoryException` nesnesi oluşturur.

```
CMemoryException();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuyu doğrudan kullanmayın, ancak [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception)genel işlevini çağırın. Bu genel işlev, daha önce ayrılmış bellekte özel durum nesnesini oluşturduğundan bir bellek yetersiz durumunda başarılı olabilir. özel durum işleme hakkında daha fazla bilgi için, bkz. [özel durumlar](../exception-handling-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[CException sınıfı](cexception-class.md)<br/>
[Hiyerarşi grafiği](../hierarchy-chart.md)
