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
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855371"
---
# <a name="carchiveexception-class"></a>CArchiveException sınıfı

Serileştirme özel durum koşulunu temsil eder

## <a name="syntax"></a>Sözdizimi

```
class CArchiveException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CArchiveException::CArchiveException](#carchiveexception)|`CArchiveException` nesnesi oluşturur.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CArchiveException:: m_cause](#m_cause)|Özel durumun nedenini gösterir.|
|[CArchiveException:: m_strFileName](#m_strfilename)|Bu özel durum koşulunun dosya adını belirtir.|

## <a name="remarks"></a>Açıklamalar

`CArchiveException` sınıfı, özel durumun nedenini gösteren bir ortak veri üyesini içerir.

`CArchiveException` nesneler, [CArchive](../../mfc/reference/carchive-class.md) üye işlevleri içinde oluşturulur ve oluşturulur. Bu nesnelere bir **catch** ifadesinin kapsamı içinde erişebilirsiniz. Nedeni kodu işletim sisteminden bağımsızdır. Özel durum işleme hakkında daha fazla bilgi için bkz. [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CArchiveException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="carchiveexception"></a>CArchiveException::CArchiveException

Nesne içindeki *nedeni* bir `CArchiveException` nesnesi oluşturur.

```
CArchiveException(
    int cause = CArchiveException::none,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Parametreler

*sağlamak*<br/>
Özel durumun nedenini gösteren numaralandırılmış tür değişkeni. Numaralandırıcıların bir listesi için [m_cause](#m_cause) veri üyesine bakın.

*lpszArchiveName*<br/>
Özel duruma neden olan `CArchive` nesnesinin adını içeren bir dizeye işaret eder.

### <a name="remarks"></a>Açıklamalar

Yığında bir `CArchiveException` nesnesi oluşturabilir ve kendiniz oluşturabilir ya da [Genel işlevin sizin](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) yerinize işlemesini sağlayabilirsiniz.

Bu oluşturucuyu doğrudan kullanmayın; Bunun yerine, `AfxThrowArchiveException`genel işlevini çağırın.

##  <a name="m_cause"></a>CArchiveException:: m_cause

Özel durumun nedenini belirtir.

```
int m_cause;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi **int**türünde ortak bir değişkendir. Değerleri `CArchiveException` numaralandırılmış bir tür tarafından tanımlanır. Numaralandırıcılar ve anlamları aşağıdaki gibidir:

- `CArchiveException::none` hata oluştu.

- Belirtilmemiş `CArchiveException::genericException` hatası.

- `CArchiveException::readOnly`, yükleme için açılan bir arşive yazmaya çalıştı.

- `CArchiveException::endOfFile` bir nesne okunurken dosyanın sonuna ulaşıldı.

- `CArchiveException::writeOnly`, depolamada açılan bir arşivden okumaya çalıştı.

- Geçersiz dosya biçimi `CArchiveException::badIndex`.

- `CArchiveException::badClass`, bir nesneyi yanlış türdeki bir nesneye okumaya çalıştı.

- `CArchiveException::badSchema`, sınıfının farklı bir sürümüyle bir nesne okumaya çalıştı.

    > [!NOTE]
    >  Bu `CArchiveException` numaralandırıcıların nedeni, `CFileException` neden numaralandırıcılarından farklıdır.

    > [!NOTE]
    > `CArchiveException::generic` kullanım dışıdır. Bunun yerine `genericException` kullanın. **Genel** bir uygulamada kullanılırsa ve/clr ile derlense, şifre çöz kolay olmayan sözdizimi hataları olur.

##  <a name="m_strfilename"></a>CArchiveException:: m_strFileName

Bu özel durum koşulunun dosya adını belirtir.

```
CString m_strFileName;
```

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CArchive Sınıfı](../../mfc/reference/carchive-class.md)<br/>
[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)<br/>
[Özel Durum İşleme](../../mfc/reference/exception-processing.md)
