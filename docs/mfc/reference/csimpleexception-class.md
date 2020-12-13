---
description: 'Daha fazla bilgi edinin: CSimpleException sınıfı'
title: CSimpleException sınıfı
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
ms.openlocfilehash: 8070604e05fa59f7fcdfef6dcaad12ab0497da9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342824"
---
# <a name="csimpleexception-class"></a>CSimpleException sınıfı

Bu sınıf, kaynak açısından kritik MFC özel durumları için temel bir sınıftır.

## <a name="syntax"></a>Syntax

```
class AFX_NOVTABLE CSimpleException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleException:: CSimpleException](#csimpleexception)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleException:: GetErrorMessage](#geterrormessage)|Oluşan bir hata hakkında metin sağlar.|

## <a name="remarks"></a>Açıklamalar

`CSimpleException` , kaynak açısından kritik MFC özel durumlarının temel sınıfıdır ve bir hata iletisinin sahipliğini ve başlatmasını işler. Aşağıdaki sınıflar `CSimpleException` temel sınıfları olarak kullanır:

|Ad|Açıklama|
|-|-|
|[CMemoryException sınıfı](../../mfc/reference/cmemoryexception-class.md)|Bellek yetersiz özel durumu|
|[CNotSupportedException sınıfı](../../mfc/reference/cnotsupportedexception-class.md)|Desteklenmeyen bir işlem için istekler|
|[CResourceException sınıfı](../../mfc/reference/cresourceexception-class.md)|Windows kaynağı bulunamadı veya oluşturulabilir değil|
|[CUserException sınıfı](../../mfc/reference/cuserexception-class.md)|Bir kaynağın bulunamadığını belirten özel durum|
|[CInvalidArgException sınıfı](../../mfc/reference/cinvalidargexception-class.md)|Geçersiz bir bağımsız değişkeni gösteren özel durum|

`CSimpleException`Soyut bir temel sınıf olduğundan, bir nesneyi doğrudan bildiremezsiniz `CSimpleException` . Bunun yerine, önceki tabloda bulunanlar gibi türetilmiş nesneleri bildirmeniz gerekir. Kendi türetilmiş sınıfınızı bildirirken, önceki sınıfları model olarak kullanın.

Daha fazla bilgi için bkz. [CException sınıfı](../../mfc/reference/cexception-class.md) konusu ve [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CSimpleException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="csimpleexceptioncsimpleexception"></a><a name="csimpleexception"></a> CSimpleException:: CSimpleException

Oluşturucu.

```
CSimpleException();
explicit CSimpleException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Parametreler

*bAutoDelete*<br/>
`CSimpleException`Nesnenin belleği yığında ayrılmışsa TRUE değerini belirtin. Bu, `CSimpleException` `Delete` özel durumu silmek için üye işlevi çağrıldığında nesnenin silinmesine neden olur. `CSimpleException`Nesne Stack içindeyse veya genel bir nesnese, false belirtin. Bu durumda, `CSimpleException` `Delete` üye işlevi çağrıldığında nesne silinmez.

### <a name="remarks"></a>Açıklamalar

Normalde bu oluşturucuyu doğrudan çağırmanız gerekmez. Özel durum oluşturan bir işlev `CException` , türetilmiş bir sınıfın örneğini oluşturmalı ve oluşturucusunu çağırmalıdır ya da önceden tanımlanmış bir tür oluşturmak Için [AFXTHROWFILEEXCEPTION](exception-processing.md#afxthrowfileexception)gibi MFC throw işlevlerinden birini kullanmalıdır.

## <a name="csimpleexceptiongeterrormessage"></a><a name="geterrormessage"></a> CSimpleException:: GetErrorMessage

Oluşan bir hata hakkında metin sağlamak için bu üye işlevi çağırın.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszError*<br/>
Bir hata iletisi alacak bir arabelleğin işaretçisi.

*nMaxError*<br/>
NULL Sonlandırıcı dahil olmak üzere, arabelleğin tutabilecek en fazla karakter sayısı.

*pnHelpContext*<br/>
Yardım bağlamı KIMLIĞINI alacak bir UINT adresi. NULL ise KIMLIK döndürülmez.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0, kullanılabilir hata iletisi metni yok.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [CException:: GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CException sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Özel Durum İşleme](../../mfc/exception-handling-in-mfc.md)
