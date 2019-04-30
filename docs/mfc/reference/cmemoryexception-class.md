---
title: CMemoryException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
ms.openlocfilehash: 11be0eba080085c507ed718ea23219ca1c93aeba
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341176"
---
# <a name="cmemoryexception-class"></a>CMemoryException sınıfı

Bellek yetersiz özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMemoryException : public CSimpleException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMemoryException::CMemoryException](#cmemoryexception)|Oluşturur bir `CMemoryException` nesne.|

## <a name="remarks"></a>Açıklamalar

Başka hiçbir nitelik gerekli veya mümkün değil. Bellek özel durumlar tarafından otomatik olarak **yeni**. Kendi bellek işlevleri yazarsanız kullanarak `malloc`için örnek, ardından bellek özel durumları atma için sorumludur.

Daha fazla bilgi için `CMemoryException`, makaleye göz atın [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CMemoryException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="cmemoryexception"></a>  CMemoryException::CMemoryException

Oluşturur bir `CMemoryException` nesne.

```
CMemoryException();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu doğrudan kullanmaz, bunun yerine genel işlev çağrısı [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). Bu genel işlev, önceden ayrılmış bellek içinde özel durum nesnesi oluşturur çünkü bir bellek yetersiz duruma başarılı olabilir. özel durum işleme hakkında daha fazla bilgi için bkz [özel durumları](../exception-handling-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](cexception-class.md)<br/>
[Hiyerarşi Grafiği](../hierarchy-chart.md)
