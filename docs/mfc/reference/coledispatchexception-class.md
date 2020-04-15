---
title: COleDispatchException Sınıf
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
ms.openlocfilehash: 4572b639b757569d8e3cfa731f99c123762f3900
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375058"
---
# <a name="coledispatchexception-class"></a>COleDispatchException Sınıf

OLE otomasyonunun önemli bir `IDispatch` parçası olan OLE arabirimine özgü özel özel durumları işler.

## <a name="syntax"></a>Sözdizimi

```
class COleDispatchException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleDispatchException::m_dwHelpContext](#m_dwhelpcontext)|Hata için yardım bağlamı.|
|[COleDispatchException::m_strDescription](#m_strdescription)|Sözlü hata açıklaması.|
|[COleDispatchException::m_strHelpFile](#m_strhelpfile)|Kullanmak için yardım `m_dwHelpContext`dosyası.|
|[COleDispatchException::m_strSource](#m_strsource)|Özel durum oluşturulan uygulama.|
|[COleDispatchException::m_wCode](#m_wcode)|`IDispatch`-belirli hata kodu.|

## <a name="remarks"></a>Açıklamalar

`CException` Taban sınıftan türetilen diğer özel `COleDispatchException` durum sınıfları gibi THROW, THROW_LAST, TRY, CATCH, AND_CATCH ve END_CATCH makroları ile kullanılabilir.

Genel olarak, bir `COleDispatchException` nesne oluşturmak ve atmak için [AfxThrowOleDispatchException'ı](exception-processing.md#afxthrowoledispatchexception) aramalısınız.

Özel durumlar hakkında daha fazla bilgi için, [Özel Durum Kullanımı (MFC)](../../mfc/exception-handling-in-mfc.md) ve [Özel Durumlar makalelerine bakın: OLE Özel Durumlar.](../../mfc/exceptions-ole-exceptions.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cexception](../../mfc/reference/cexception-class.md)

`COleDispatchException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="coledispatchexceptionm_dwhelpcontext"></a><a name="m_dwhelpcontext"></a>COleDispatchException::m_dwHelpContext

Uygulamanızın yardım (. HLP) dosyası.

```
DWORD m_dwHelpContext;
```

### <a name="remarks"></a>Açıklamalar

Bu üye, bir özel durum atıldığında [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) işlevi tarafından ayarlanır.

### <a name="example"></a>Örnek

  [COleDispatchDriver örneğine bakın:CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

## <a name="coledispatchexceptionm_strdescription"></a><a name="m_strdescription"></a>COleDispatchException::m_strDescription

"Disk tam" gibi sözlü bir hata açıklaması içerir.

```
CString m_strDescription;
```

### <a name="remarks"></a>Açıklamalar

Bu üye, bir özel durum atıldığında [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) işlevi tarafından ayarlanır.

### <a name="example"></a>Örnek

  [COleDispatchDriver örneğine bakın:CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

## <a name="coledispatchexceptionm_strhelpfile"></a><a name="m_strhelpfile"></a>COleDispatchException::m_strHelpFile

Çerçeve, bu dizeyi uygulamanın yardım dosyasının adı ile doldurur.

```
CString m_strHelpFile;
```

## <a name="coledispatchexceptionm_strsource"></a><a name="m_strsource"></a>COleDispatchException::m_strSource

Çerçeve, bu dizeyi özel durumu oluşturan uygulamanın adıile doldurur.

```
CString m_strSource;
```

### <a name="example"></a>Örnek

  [COleDispatchDriver örneğine bakın:CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).

## <a name="coledispatchexceptionm_wcode"></a><a name="m_wcode"></a>COleDispatchException::m_wCode

Uygulamanıza özgü bir hata kodu içerir.

```
WORD m_wCode;
```

### <a name="remarks"></a>Açıklamalar

Bu üye, bir özel durum atıldığında [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) işlevi tarafından ayarlanır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDispatchDriver Sınıfı](../../mfc/reference/coledispatchdriver-class.md)<br/>
[COleException Sınıfı](../../mfc/reference/coleexception-class.md)
