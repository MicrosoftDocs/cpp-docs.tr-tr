---
title: Cınvalidargexception sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
dev_langs:
- C++
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cff0727f1d194982ad76d24b0a91875448ea45c0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389819"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSimpleException Sınıfı](../../mfc/reference/csimpleexception-class.md)
