---
title: COleException Sınıfı
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
ms.openlocfilehash: 737c9e669990f4de6ae18cdc7662c131ad61516f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375007"
---
# <a name="coleexception-class"></a>COleException Sınıfı

OLE işlemiyle ilgili bir özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class COleException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleException::Process](#process)|Yakalanan bir özel durumu OLE iade koduna çevirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleException::m_sc](#m_sc)|Özel durum nedenini gösteren durum kodunu içerir.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `COleException` özel durumun nedenini belirten durum kodunu tutan ortak bir veri üyesi içerir.

Genel olarak, doğrudan bir `COleException` nesne oluşturmamalısınız; bunun yerine, [AfxThrowOleException](exception-processing.md#afxthrowoleexception)çağırmalısınız.

Özel durumlar hakkında daha fazla bilgi için, [Özel Durum Kullanımı (MFC)](../../mfc/exception-handling-in-mfc.md) ve [Özel Durumlar makalelerine bakın: OLE Özel Durumlar.](../../mfc/exceptions-ole-exceptions.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cexception](../../mfc/reference/cexception-class.md)

`COleException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="coleexceptionm_sc"></a><a name="m_sc"></a>COleException::m_sc

Bu veri üyesi, özel durumun nedenini gösteren OLE durum kodunu tutar.

```
SCODE m_sc;
```

### <a name="remarks"></a>Açıklamalar

Bu değişkenin değeri [AfxThrowOleException](exception-processing.md#afxthrowoleexception)tarafından ayarlanır.

SCODE hakkında daha fazla bilgi için Windows SDK'daki [COM Hata Kodlarının Yapısı'na](/windows/win32/com/structure-of-com-error-codes) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]

## <a name="coleexceptionprocess"></a><a name="process"></a>COleException::Process

Yakalanan bir özel durumu OLE durum koduna çevirmek için **İşlem** üye işlevini arayın.

```
static SCODE PASCAL Process(const CException* pAnyException);
```

### <a name="parameters"></a>Parametreler

*pAnyException*<br/>
Yakalanan bir özel durum için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

OLE durum kodu.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu işlev **statiktir.**

SCODE hakkında daha fazla bilgi için Windows SDK'daki [COM Hata Kodlarının Yapısı'na](/windows/win32/com/structure-of-com-error-codes) bakın.

### <a name="example"></a>Örnek

  [COleDispatchDriver örneğine bakın:CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
