---
description: 'Daha fazla bilgi edinin: Cotadispatchexception sınıfı'
title: Cotadispatchexception sınıfı
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
ms.openlocfilehash: 39d8c4652f49b721e5f94c05319e5c1adad07269
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227214"
---
# <a name="coledispatchexception-class"></a>Cotadispatchexception sınıfı

OLE `IDispatch` otomasyonunun önemli bir parçası olan OLE arabirimine özgü özel durumları işler.

## <a name="syntax"></a>Syntax

```
class COleDispatchException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cotadispatchexception:: m_dwHelpContext](#m_dwhelpcontext)|Hata için yardım bağlamı.|
|[Cotadispatchexception:: m_strDescription](#m_strdescription)|Cobilanço hatası açıklaması.|
|[Cotadispatchexception:: m_strHelpFile](#m_strhelpfile)|İle kullanılacak yardım dosyası `m_dwHelpContext` .|
|[Cotadispatchexception:: m_strSource](#m_strsource)|Özel durumu oluşturan uygulama.|
|[Cotadispatchexception:: m_wCode](#m_wcode)|`IDispatch`-özel hata kodu.|

## <a name="remarks"></a>Açıklamalar

Temel sınıftan türetilmiş diğer özel durum sınıfları gibi `CException` , `COleDispatchException` THROW, THROW_LAST, TRY, CATCH, AND_CATCH ve END_CATCH makrolarıyla birlikte kullanılabilir.

Genel olarak, bir nesne oluşturmak ve oluşturmak için [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) öğesini çağırmanız gerekir `COleDispatchException` .

Özel durumlar hakkında daha fazla bilgi için bkz. makalelere [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md) ve [özel durumlar: OLE özel durumları](../../mfc/exceptions-ole-exceptions.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`COleDispatchException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="coledispatchexceptionm_dwhelpcontext"></a><a name="m_dwhelpcontext"></a> Cotadispatchexception:: m_dwHelpContext

Uygulamanızın yardımında bir yardım bağlamı tanımlar (. HLP) dosyası.

```
DWORD m_dwHelpContext;
```

### <a name="remarks"></a>Açıklamalar

Bu üye, bir özel durum oluştuğunda [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) işlevi tarafından ayarlanır.

### <a name="example"></a>Örnek

  [Cotadispatchdriver:: CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)örneğine bakın.

## <a name="coledispatchexceptionm_strdescription"></a><a name="m_strdescription"></a> Cotadispatchexception:: m_strDescription

"Disk dolu" gibi bir ifade hatası açıklaması içerir.

```
CString m_strDescription;
```

### <a name="remarks"></a>Açıklamalar

Bu üye, bir özel durum oluştuğunda [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) işlevi tarafından ayarlanır.

### <a name="example"></a>Örnek

  [Cotadispatchdriver:: CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)örneğine bakın.

## <a name="coledispatchexceptionm_strhelpfile"></a><a name="m_strhelpfile"></a> Cotadispatchexception:: m_strHelpFile

Çerçeve bu dizeyi uygulamanın Yardım dosyası adıyla doldurur.

```
CString m_strHelpFile;
```

## <a name="coledispatchexceptionm_strsource"></a><a name="m_strsource"></a> Cotadispatchexception:: m_strSource

Çerçeve bu dizeyi, özel durumu oluşturan uygulamanın adıyla doldurur.

```
CString m_strSource;
```

### <a name="example"></a>Örnek

  [Cotadispatchdriver:: CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)örneğine bakın.

## <a name="coledispatchexceptionm_wcode"></a><a name="m_wcode"></a> Cotadispatchexception:: m_wCode

Uygulamanıza özel bir hata kodu içerir.

```
WORD m_wCode;
```

### <a name="remarks"></a>Açıklamalar

Bu üye, bir özel durum oluştuğunda [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) işlevi tarafından ayarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[CException sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Cotadispatchdriver sınıfı](../../mfc/reference/coledispatchdriver-class.md)<br/>
[Cotaexception sınıfı](../../mfc/reference/coleexception-class.md)
