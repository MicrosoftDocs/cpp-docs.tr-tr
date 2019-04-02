---
title: COleDispatchException sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
helpviewer_keywords:
- COleDispatchException [MFC], m_dwHelpContext
- COleDispatchException [MFC], m_strDescription
- COleDispatchException [MFC], m_strHelpFile
- COleDispatchException [MFC], m_strSource
- COleDispatchException [MFC], m_wCode
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
ms.openlocfilehash: 2d5b9d2a0dc1e716ea8cb20f0d0dcb4c5d765079
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769062"
---
# <a name="coledispatchexception-class"></a>COleDispatchException sınıfı

OLE belirli özel durumları işler `IDispatch` arabirimi OLE otomasyonunun önemli bir parçasıdır.

## <a name="syntax"></a>Sözdizimi

```
class COleDispatchException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleDispatchException::m_dwHelpContext](#m_dwhelpcontext)|Hata için Yardım bağlamı.|
|[COleDispatchException::m_strDescription](#m_strdescription)|Sözlü hata açıklaması.|
|[COleDispatchException::m_strHelpFile](#m_strhelpfile)|Yardım dosyası ile kullanılacak `m_dwHelpContext`.|
|[COleDispatchException::m_strSource](#m_strsource)|Özel durumu oluşturan uygulama.|
|[COleDispatchException::m_wCode](#m_wcode)|`IDispatch`-belirli bir hata kodu.|

## <a name="remarks"></a>Açıklamalar

Türetilen bir özel durum sınıfları gibi `CException` temel sınıfı, `COleDispatchException` THROW, THROW_LAST, TRY, CATCH, AND_CATCH ve END_CATCH makroları ile kullanılabilir.

Genel olarak, çağırmalıdır [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) oluşturup throw bir `COleDispatchException` nesne.

Özel durumları hakkında daha fazla bilgi için bkz: makaleleri [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: OLE özel durumları](../../mfc/exceptions-ole-exceptions.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleDispatchException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

##  <a name="m_dwhelpcontext"></a>  COleDispatchException::m_dwHelpContext

Uygulamanızın Yardımı'nda Yardım içeriğini tanımlayan (. HLP) dosyası.

```
DWORD m_dwHelpContext;
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından ayarlanan [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) bir özel durum harekete geçirildiğinde.

### <a name="example"></a>Örnek

  Örneğin bakın [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

##  <a name="m_strdescription"></a>  COleDispatchException::m_strDescription

"Disk dolu." gibi sözlü hata açıklamasını içerir

```
CString m_strDescription;
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından ayarlanan [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) bir özel durum harekete geçirildiğinde.

### <a name="example"></a>Örnek

  Örneğin bakın [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

##  <a name="m_strhelpfile"></a>  COleDispatchException::m_strHelpFile

Uygulamanın Yardım dosyasının adı Bu dizeyle framework doldurur.

```
CString m_strHelpFile;
```

##  <a name="m_strsource"></a>  COleDispatchException::m_strSource

Framework özel durumu oluşturan uygulama adı Bu dizeyle doldurur.

```
CString m_strSource;
```

### <a name="example"></a>Örnek

  Örneğin bakın [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

##  <a name="m_wcode"></a>  COleDispatchException::m_wCode

Uygulamanıza özgü bir hata kodunu içerir.

```
WORD m_wCode;
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi tarafından ayarlanan [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) bir özel durum harekete geçirildiğinde.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDispatchDriver Sınıfı](../../mfc/reference/coledispatchdriver-class.md)<br/>
[COleException Sınıfı](../../mfc/reference/coleexception-class.md)
