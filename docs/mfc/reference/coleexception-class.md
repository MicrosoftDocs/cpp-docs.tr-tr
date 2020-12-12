---
description: 'Daha fazla bilgi edinin: Coelexception sınıfı'
title: Cotaexception sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
ms.openlocfilehash: cb11e9c285180c6e54701c210c5329714d7dccb0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227097"
---
# <a name="coleexception-class"></a>Cotaexception sınıfı

OLE işlemiyle ilgili bir özel durum koşulunu temsil eder.

## <a name="syntax"></a>Syntax

```
class COleException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotaexception::P rocess](#process)|Yakalanan bir özel durumu OLE dönüş koduna çevirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cotaexception:: m_sc](#m_sc)|Özel durumun nedenini gösteren durum kodunu içerir.|

## <a name="remarks"></a>Açıklamalar

`COleException`Sınıfı, özel durumun nedenini gösteren durum kodunu tutan bir ortak veri üyesini içerir.

Genel olarak, doğrudan bir nesne oluşturmamalıdır `COleException` ; bunun yerine [AfxThrowOleException](exception-processing.md#afxthrowoleexception)çağırmalısınız.

Özel durumlar hakkında daha fazla bilgi için bkz. makalelere [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: OLE özel durumları](../../mfc/exceptions-ole-exceptions.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="coleexceptionm_sc"></a><a name="m_sc"></a> Cotaexception:: m_sc

Bu veri üyesi, özel durumun nedenini gösteren OLE durum kodunu tutar.

```
SCODE m_sc;
```

### <a name="remarks"></a>Açıklamalar

Bu değişkenin değeri [AfxThrowOleException](exception-processing.md#afxthrowoleexception)tarafından ayarlanır.

SCODE hakkında daha fazla bilgi için bkz. Windows SDK [com hata kodları yapısı](/windows/win32/com/structure-of-com-error-codes) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]

## <a name="coleexceptionprocess"></a><a name="process"></a> Cotaexception::P rocess

Yakalanan bir özel durumu OLE durum koduna çevirmek için **Process** member işlevini çağırın.

```
static SCODE PASCAL Process(const CException* pAnyException);
```

### <a name="parameters"></a>Parametreler

*Panrivexception*<br/>
Yakalanan özel durum işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

OLE durum kodu.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu işlev **`static`** .

SCODE hakkında daha fazla bilgi için bkz. Windows SDK [com hata kodları yapısı](/windows/win32/com/structure-of-com-error-codes) .

### <a name="example"></a>Örnek

  [Cotadispatchdriver:: CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[CException sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
