---
title: CSimpleException Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
ms.openlocfilehash: eb94ba9e3d26b3cd910f23c3d4abb29d3b8b1cd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318358"
---
# <a name="csimpleexception-class"></a>CSimpleException Sınıfı

Bu sınıf, kaynak açısından kritik MFC özel durumları için bir taban sınıftır.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CSimpleException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleException::CSimpleException](#csimpleexception)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleException::GetErrorMessage](#geterrormessage)|Oluşan bir hata yla ilgili metin sağlar.|

## <a name="remarks"></a>Açıklamalar

`CSimpleException`kaynak açısından kritik MFC özel durumları için taban sınıftır ve bir hata iletisinin sahipliğini ve başlatılmasını işler. Aşağıdaki sınıflar `CSimpleException` taban sınıf olarak kullanılır:

|||
|-|-|
|[CMemoryException Sınıfı](../../mfc/reference/cmemoryexception-class.md)|Bellek dışı özel durum|
|[CNotSupportedException Sınıfı](../../mfc/reference/cnotsupportedexception-class.md)|Desteklenmeyen bir işlem için istekler|
|[CResourceException Sınıf](../../mfc/reference/cresourceexception-class.md)|Windows kaynağı bulunamadı veya güvenilir değil|
|[CUserException Sınıf](../../mfc/reference/cuserexception-class.md)|Kaynağın bulunamadıgini belirten özel durum|
|[CInvalidArgException Sınıf](../../mfc/reference/cinvalidargexception-class.md)|Geçersiz bir bağımsız değişkeni gösteren özel durum|

Soyut `CSimpleException` bir taban sınıf olduğundan, `CSimpleException` bir nesneyi doğrudan bildiremezsiniz. Bunun yerine, önceki tablodaki ler gibi türetilmiş nesneleri bildirmeniz gerekir. Kendi türemiş sınıfınızı beyan ediyorsanız, önceki sınıfları model olarak kullanın.

Daha fazla bilgi için [CException Class](../../mfc/reference/cexception-class.md) konusuna ve [Özel Durum İşleme (MFC)](../../mfc/exception-handling-in-mfc.md)konusuna bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cexception](../../mfc/reference/cexception-class.md)

`CSimpleException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="csimpleexceptioncsimpleexception"></a><a name="csimpleexception"></a>CSimpleException::CSimpleException

Oluşturucu.

```
CSimpleException();
explicit CSimpleException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Parametreler

*bAutoDelete*<br/>
Nesnenin belleği yığına ayrılmışsa `CSimpleException` DOĞRU'yu belirtin. Bu, üye `CSimpleException` işlev özel durumu `Delete` silmek için çağrıldığında nesnenin silinmesine neden olur. `CSimpleException` Nesne yığındaysa veya genel bir nesneyse FALSE belirtin. Bu durumda, `CSimpleException` `Delete` üye işlev çağrıldığında nesne silinmez.

### <a name="remarks"></a>Açıklamalar

Normalde bu yapıcıyı doğrudan aramanız gerekmez. Özel durum atan bir işlev, türemiş bir `CException`sınıfın bir örneğini oluşturmalı ve oluşturucuyu çağırmalıdır veya önceden tanımlanmış bir tür atmak için [AfxThrowFileException](exception-processing.md#afxthrowfileexception)gibi MFC atma işlevlerinden birini kullanmalıdır.

## <a name="csimpleexceptiongeterrormessage"></a><a name="geterrormessage"></a>CSimpleException::GetErrorMessage

Oluşan bir hata yla ilgili metin sağlamak için bu üye işlevi arayın.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszHata*<br/>
Hata iletisi alacak arabellek için bir işaretçi.

*nMaxHatası*<br/>
NULL sonlandırıcısı da dahil olmak üzere arabellek tutabileceği maksimum karakter sayısı.

*pnHelpContext*<br/>
Yardım bağlam kimliği alacak bir UINT adresi. NULL durumunda, hiçbir kimlik döndürülür.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; aksi takdirde 0 hata iletisi metni yoksa.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Bkz. CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Özel Durum İşleme](../../mfc/exception-handling-in-mfc.md)
