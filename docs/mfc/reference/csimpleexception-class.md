---
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
ms.openlocfilehash: aa36fc0ac0eed5ea760224f9e0a3af1c97e18895
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324096"
---
# <a name="csimpleexception-class"></a>CSimpleException sınıfı

Bu sınıf, kaynak kritik MFC özel durumları için temel sınıftır.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CSimpleException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleException::CSimpleException](#csimpleexception)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleException::GetErrorMessage](#geterrormessage)|Gerçekleşen bir hata hakkında daha fazla metin sağlar.|

## <a name="remarks"></a>Açıklamalar

`CSimpleException` Kaynak kritik MFC özel durumları için temel sınıf ve sahiplik ve bir hata iletisinin başlatma işler. Aşağıdaki sınıflar kullanım `CSimpleException` kendi temel sınıf olarak:

|||
|-|-|
|[CMemoryException Sınıfı](../../mfc/reference/cmemoryexception-class.md)|Bellek yetersiz özel durumu|
|[CNotSupportedException Sınıfı](../../mfc/reference/cnotsupportedexception-class.md)|Desteklenmeyen bir işlem istekleri|
|[CResourceException Sınıfı](../../mfc/reference/cresourceexception-class.md)|Windows kaynak bulunamadı veya değil|
|[CUserException Sınıfı](../../mfc/reference/cuserexception-class.md)|Bir kaynağı gösteren özel durum bulunamadı|
|[CInvalidArgException Sınıfı](../../mfc/reference/cinvalidargexception-class.md)|Geçersiz bağımsız değişken gösteren durum|

Çünkü `CSimpleException` bildirip soyut bir temel sınıf olan bir `CSimpleException` doğrudan nesne. Bunun yerine, önceki tabloda bulunanlar gibi türetilmiş nesneler bildirmeniz gerekir. Türetilmiş sınıfınızın bildiriliyorsa önceki sınıflarını model olarak kullanın.

Daha fazla bilgi için [CException sınıfı](../../mfc/reference/cexception-class.md) konu ve [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CSimpleException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="csimpleexception"></a>  CSimpleException::CSimpleException

Oluşturucu.

```
CSimpleException();
explicit CSimpleException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Parametreler

*bAutoDelete*<br/>
TRUE ise belirtmek için bellek `CSimpleException` nesneyi yığında ayrılmış. Bu neden `CSimpleException` ne zaman Silinmiş nesne `Delete` üye işlevi, özel durum silmek için çağrılır. FALSE belirtin `CSimpleException` nesne yığında veya genel bir nesnedir. Bu durumda, `CSimpleException` nesne olmayacak ne zaman silinmiş `Delete` üye işlevi çağrılır.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucu doğrudan çağırmak hiçbir zaman normalde gerekir. Özel durum oluşturan bir işlev bir örneğini oluşturmanız gerekir bir `CException`-türetilmiş sınıf ve MFC'nin kullanımı throw işlevleri gibi oluşturucu veya çağrı [AfxThrowFileException](exception-processing.md#afxthrowfileexception), önceden tanımlanmış bir tür oluşturmak için.

##  <a name="geterrormessage"></a>  CSimpleException::GetErrorMessage

Metin gerçekleşen bir hata hakkında sağlamaya bu üye işlevini çağırın.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszError*<br/>
Bir ileti alacak arabellek için işaretçi.

*nMaxError*<br/>
Arabellek tutabilir, NULL sonlandırıcıyı da dahil olmak üzere karakter sayısı.

*pnHelpContext*<br/>
Yardım içeriği kimliği alacak bir UINT adresi NULL ise, hiçbir kimliği döndürülür.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde hata iletisi 0 kullanılabilir.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Özel Durum İşleme](../../mfc/exception-handling-in-mfc.md)
