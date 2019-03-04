---
title: CArchiveException sınıfı
ms.date: 11/04/2016
f1_keywords:
- CArchiveException
- AFX/CArchiveException
- AFX/CArchiveException::CArchiveException
- AFX/CArchiveException::m_cause
- AFX/CArchiveException::m_strFileName
helpviewer_keywords:
- CArchiveException [MFC], CArchiveException
- CArchiveException [MFC], m_cause
- CArchiveException [MFC], m_strFileName
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
ms.openlocfilehash: 731735bccf9225e67d82b1fe90336c92a630b368
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283572"
---
# <a name="carchiveexception-class"></a>CArchiveException sınıfı

Seri hale getirme özel durum koşulunu temsil eder

## <a name="syntax"></a>Sözdizimi

```
class CArchiveException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CArchiveException::CArchiveException](#carchiveexception)|Oluşturur bir `CArchiveException` nesne.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CArchiveException::m_cause](#m_cause)|Özel durum nedenini gösterir.|
|[CArchiveException::m_strFileName](#m_strfilename)|Bu özel durum koşulunu dosyasının adını belirtir.|

## <a name="remarks"></a>Açıklamalar

`CArchiveException` Sınıfı özel durumun nedenini belirten bir genel veri üyesi içerir.

`CArchiveException` nesneleri oluşturulur ve içinde oluşan [CArchive](../../mfc/reference/carchive-class.md) üye işlevleri. Bu nesneler kapsamında erişebileceğiniz bir **CATCH** ifade. İşletim sistemi neden kodu bağımsızdır. Özel durum işleme hakkında daha fazla bilgi için bkz. [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CArchiveException`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="carchiveexception"></a>  CArchiveException::CArchiveException

Oluşturur bir `CArchiveException` değerini depolama nesnesi *neden* nesnesindeki.

```
CArchiveException(
    int cause = CArchiveException::none,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Parametreler

*Bunun nedeni*<br/>
Özel durumun nedenini gösteren bir listeden seçimli türü değişkeni. Numaralandırıcıların listesi için bkz. [m_cause](#m_cause) veri üyesi.

*lpszArchiveName*<br/>
İşaret adı içeren bir dizeye `CArchive` özel duruma neden olan nesne.

### <a name="remarks"></a>Açıklamalar

Oluşturabileceğiniz bir `CArchiveException` yığında nesne ve kendiniz throw veya genel işlev izin [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) sizin için yapar.

Bu oluşturucu doğrudan kullanmayın; Bunun yerine, genel işlev çağrısı `AfxThrowArchiveException`.

##  <a name="m_cause"></a>  CArchiveException::m_cause

Özel durumun nedenini belirtir.

```
int m_cause;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi türünün genel bir değişkendir **int**. Değerleri tarafından tanımlanan bir `CArchiveException` listelenmiş türü. Numaralandırıcılar ve bunların anlamlarını açıklayan aşağıdaki gibidir:

- `CArchiveException::none` Herhangi bir hata oluştu.

- `CArchiveException::genericException` Belirlenemeyen hata.

- `CArchiveException::readOnly` Yükleme için açılan bir arşivde yazılacak çalıştı.

- `CArchiveException::endOfFile` Ulaşıldığında bir nesne okunurken dosya sonu.

- `CArchiveException::writeOnly` Depolamak için açılan bir arşivde okuma denedi.

- `CArchiveException::badIndex` Dosya biçimi geçersiz.

- `CArchiveException::badClass` Nesnenin yanlış türde bir nesnede okuma denedi.

- `CArchiveException::badSchema` Farklı bir sürüm sınıfının bir nesnesiyle okuma denedi.

    > [!NOTE]
    >  Bunlar `CArchiveException` neden numaralandırıcılar kodundan `CFileException` numaralandırıcılar neden olur.

    > [!NOTE]
    > `CArchiveException::generic` kullanım dışı bırakılmıştır. Bunun yerine `genericException` kullanın. Varsa **genel** bir uygulamada kullanılan ve yerleşik/CLR ile olacaktır söz dizimi hataları çözmek kolay değildir.

##  <a name="m_strfilename"></a>  CArchiveException::m_strFileName

Bu özel durum koşulunu dosyasının adını belirtir.

```
CString m_strFileName;
```

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CArchive Sınıfı](../../mfc/reference/carchive-class.md)<br/>
[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)<br/>
[Özel Durum İşleme](../../mfc/reference/exception-processing.md)
