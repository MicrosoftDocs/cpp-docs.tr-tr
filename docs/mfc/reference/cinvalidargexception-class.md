---
title: CInvalidArgException Sınıf
ms.date: 11/04/2016
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
ms.openlocfilehash: b28b6e84043b85a8117694a67ff5fff13e7c786b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372372"
---
# <a name="cinvalidargexception-class"></a>CInvalidArgException Sınıf

Bu sınıf geçersiz bir bağımsız değişken özel durum temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CInvalidArgException : public CSimpleException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CInvalidArgİst::CInvalidArgİstis](#cinvalidargexception)|Oluşturucu.|

## <a name="remarks"></a>Açıklamalar

Nesne `CInvalidArgException` geçersiz bir bağımsız değişken özel durum temsil eder.

Özel Durum İşleme hakkında daha fazla bilgi için [CException Class](../../mfc/reference/cexception-class.md) konusuna ve [Özel Durum İşleme (MFC)](../../mfc/exception-handling-in-mfc.md)konusuna bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cexception](../../mfc/reference/cexception-class.md)

[Csimpleexception](../../mfc/reference/csimpleexception-class.md)

`CInvalidArgException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cinvalidargexceptioncinvalidargexception"></a><a name="cinvalidargexception"></a>CInvalidArgİst::CInvalidArgİstis

Oluşturucu.

```
CInvalidArgException();
```

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuya doğrudan kullanmayın; global fonksiyon **AfxThrowInvalidArgException**arayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CSimpleException Sınıfı](../../mfc/reference/csimpleexception-class.md)
