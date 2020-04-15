---
title: CArchiveException Sınıfı
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
ms.openlocfilehash: ad2a9d8c5b4466a04b5a88fcce7679911bf1b81a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377007"
---
# <a name="carchiveexception-class"></a>CArchiveException Sınıfı

Serileştirme özel durum koşulunu temsil eder

## <a name="syntax"></a>Sözdizimi

```
class CArchiveException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CArchiveException::CArchiveException](#carchiveexception)|Bir `CArchiveException` nesne inşa eder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CArchiveException::m_cause](#m_cause)|Özel durum nedenini gösterir.|
|[CArchiveException::m_strFileName](#m_strfilename)|Bu özel durum durumu için dosyanın adını belirtir.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CArchiveException` özel durum nedenini gösteren bir ortak veri üyesi içerir.

`CArchiveException`nesneler oluşturulur ve [CArchive](../../mfc/reference/carchive-class.md) üye işlevleri içine atılır. Catch **ifadesi** kapsamında bu nesnelere erişebilirsiniz. Neden kodu işletim sisteminden bağımsızdır. Özel durum işleme hakkında daha fazla bilgi için [bkz.](../../mfc/exception-handling-in-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cexception](../../mfc/reference/cexception-class.md)

`CArchiveException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="carchiveexceptioncarchiveexception"></a><a name="carchiveexception"></a>CArchiveException::CArchiveException

Neden değerini `CArchiveException` *nesnede* depolayarak bir nesne inşa eder.

```
CArchiveException(
    int cause = CArchiveException::none,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Parametreler

*Neden*<br/>
Özel durum nedenini gösteren numaralandırılmış bir tür değişkeni. Sonlandırıcıların listesi için [m_cause](#m_cause) veri üyesine bakın.

*lpszArchiveName*<br/>
Özel durum neden `CArchive` nesnenin adını içeren bir dize işaret eder.

### <a name="remarks"></a>Açıklamalar

Yığın üzerinde `CArchiveException` bir nesne oluşturabilir ve kendiniz atmak veya küresel işlevi [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) sizin için ele sağlar.

Bu oluşturucuya doğrudan kullanmayın; bunun yerine, genel `AfxThrowArchiveException`işlevi arayın.

## <a name="carchiveexceptionm_cause"></a><a name="m_cause"></a>CArchiveException::m_cause

Özel durum nedenini belirtir.

```
int m_cause;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi, **int**türünden genel bir değişkendir. Değerleri numaralandırılmış bir `CArchiveException` tür tarafından tanımlanır. Sayısallaştırıcılar ve anlamları aşağıdaki gibidir:

- `CArchiveException::none`Hata oluşmadı.

- `CArchiveException::genericException`Belirtilmemiş hata.

- `CArchiveException::readOnly`Yükleme için açılan bir arşive yazmaya çalıştım.

- `CArchiveException::endOfFile`Bir nesneyi okurken dosyanın sonuna ulaşıldı.

- `CArchiveException::writeOnly`Saklamak için açılan bir arşivden okumaya çalıştım.

- `CArchiveException::badIndex`Geçersiz dosya biçimi.

- `CArchiveException::badClass`Bir nesneyi yanlış türde bir nesneye okumaya çalıştım.

- `CArchiveException::badSchema`Sınıfın farklı bir sürümü olan bir nesneyi okumaya çalıştım.

    > [!NOTE]
    >  Bu `CArchiveException` neden sayısallaştırıcılar `CFileException` neden sayısalatörler farklıdır.

    > [!NOTE]
    > `CArchiveException::generic`amortismana lı. Bunun yerine `genericException` kullanın. **Genel bir** uygulamada kullanılır ve /clr ile oluşturulmuşsa, deşifre edilmesi kolay olmayan sözdizimi hataları olacaktır.

## <a name="carchiveexceptionm_strfilename"></a><a name="m_strfilename"></a>CArchiveException::m_strFileName

Bu özel durum durumu için dosyanın adını belirtir.

```
CString m_strFileName;
```

## <a name="see-also"></a>Ayrıca bkz.

[CException Sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CArchive Sınıfı](../../mfc/reference/carchive-class.md)<br/>
[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)<br/>
[Özel Durum İşleme](../../mfc/reference/exception-processing.md)
