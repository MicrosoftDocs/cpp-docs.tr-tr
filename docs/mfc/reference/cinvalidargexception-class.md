---
description: 'Daha fazla bilgi edinin: CInvalidArgException sınıfı'
title: CInvalidArgException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
ms.openlocfilehash: f68642747a81d1c45a8246f4f25abfb8b79c81d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202801"
---
# <a name="cinvalidargexception-class"></a>CInvalidArgException sınıfı

Bu sınıf geçersiz bir bağımsız değişken özel durum koşulunu temsil eder.

## <a name="syntax"></a>Syntax

```
class CInvalidArgException : public CSimpleException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInvalidArgException:: CInvalidArgException](#cinvalidargexception)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

`CInvalidArgException`Nesne geçersiz bir bağımsız değişken özel durum koşulunu temsil eder.

Özel durum Işleme hakkında daha fazla bilgi için bkz. [CException sınıfı](../../mfc/reference/cexception-class.md) konusu ve [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CInvalidArgException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="cinvalidargexceptioncinvalidargexception"></a><a name="cinvalidargexception"></a> CInvalidArgException:: CInvalidArgException

Oluşturucu.

```
CInvalidArgException();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuyu doğrudan kullanmayın; **AfxThrowInvalidArgException** genel işlevini çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSimpleException sınıfı](../../mfc/reference/csimpleexception-class.md)
