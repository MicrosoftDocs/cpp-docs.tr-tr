---
title: Cınvalidargexception sınıfı
ms.date: 11/04/2016
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
ms.openlocfilehash: d2df9b482fe95ad0a13a85a51037a4cbbc28d057
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260198"
---
# <a name="cinvalidargexception-class"></a>Cınvalidargexception sınıfı

Bu sınıf, geçersiz bağımsız değişken özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CInvalidArgException : public CSimpleException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInvalidArgException::CInvalidArgException](#cinvalidargexception)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

A `CInvalidArgException` nesnesi geçersiz bağımsız değişken özel durum koşulunu temsil eder.

Özel durum işleme hakkında daha fazla bilgi için bkz: [CException sınıfı](../../mfc/reference/cexception-class.md) konu ve [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CInvalidArgException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="cinvalidargexception"></a>  CInvalidArgException::CInvalidArgException

Oluşturucu.

```
CInvalidArgException();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu doğrudan kullanmayın; genel işlev çağrısı **AfxThrowInvalidArgException**.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSimpleException Sınıfı](../../mfc/reference/csimpleexception-class.md)
