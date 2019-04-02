---
title: COleException sınıfı
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
ms.openlocfilehash: 6874df550103abf727573d8e34b8adadd9643db8
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767814"
---
# <a name="coleexception-class"></a>COleException sınıfı

Bir OLE işlemiyle ilgili bir özel durum koşulunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class COleException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleException::Process](#process)|OLE dönüş koda yakalanan bir özel durumu çevirir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleException::m_sc](#m_sc)|Özel durumun nedenini gösteren durum kodu içerir.|

## <a name="remarks"></a>Açıklamalar

`COleException` Sınıfı özel durumun nedenini gösteren durum kodunu içeren bir genel veri üyesi içerir.

Genel olarak, değil oluşturacağınız bir `COleException` doğrudan; bunun yerine, çağırmalıdır nesne [AfxThrowOleException](exception-processing.md#afxthrowoleexception).

Özel durumları hakkında daha fazla bilgi için bkz: makaleleri [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: OLE özel durumları](../../mfc/exceptions-ole-exceptions.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

##  <a name="m_sc"></a>  COleException::m_sc

Bu veri üyesi, özel durumun nedenini gösteren OLE durum kodu içerir.

```
SCODE m_sc;
```

### <a name="remarks"></a>Açıklamalar

Bu değişkenin değeri ayarlanır [AfxThrowOleException](exception-processing.md#afxthrowoleexception).

SCODE hakkında daha fazla bilgi için bkz. [yapısı COM hata kodlarını](/windows/desktop/com/structure-of-com-error-codes) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]

##  <a name="process"></a>  COleException::Process

Çağrı **işlem** yakalanan bir özel durumu bir OLE durumu koda çevirmek için üye işlevi.

```
static SCODE PASCAL Process(const CException* pAnyException);
```

### <a name="parameters"></a>Parametreler

*pAnyException*<br/>
Özel durum yakalandı işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

OLE durum kodu.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu işlev, **statik**.

SCODE hakkında daha fazla bilgi için bkz. [yapısı COM hata kodlarını](/windows/desktop/com/structure-of-com-error-codes) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
