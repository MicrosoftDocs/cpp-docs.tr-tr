---
title: CMemoryException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
dev_langs:
- C++
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df664db673ee3989d689b8cf28b87cfff32a8dc7
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076821"
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

## <a name="see-also"></a>Ayrıca Bkz.

[CException Sınıfı](cexception-class.md)<br/>
[Hiyerarşi Grafiği](../hierarchy-chart.md)

