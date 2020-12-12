---
description: 'Daha fazla bilgi edinin: CArchiveException Class'
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
ms.openlocfilehash: ce8355583e0a7a3fd8a382873a0e4b2a1ea91b83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185407"
---
# <a name="carchiveexception-class"></a>CArchiveException sınıfı

Serileştirme özel durum koşulunu temsil eder

## <a name="syntax"></a>Syntax

```
class CArchiveException : public CException
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CArchiveException::CArchiveException](#carchiveexception)|Bir `CArchiveException` nesnesi oluşturur.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CArchiveException:: m_cause](#m_cause)|Özel durumun nedenini gösterir.|
|[CArchiveException:: m_strFileName](#m_strfilename)|Bu özel durum koşulunun dosya adını belirtir.|

## <a name="remarks"></a>Açıklamalar

`CArchiveException`Sınıfı, özel durumun nedenini gösteren bir ortak veri üyesini içerir.

`CArchiveException` nesneler, [CArchive](../../mfc/reference/carchive-class.md) üye işlevleri içinde oluşturulur ve oluşturulur. Bu nesnelere bir **catch** ifadesinin kapsamı içinde erişebilirsiniz. Nedeni kodu işletim sisteminden bağımsızdır. Özel durum işleme hakkında daha fazla bilgi için bkz. [özel durum işleme (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CArchiveException`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="carchiveexceptioncarchiveexception"></a><a name="carchiveexception"></a> CArchiveException::CArchiveException

Nesne oluşturur ve `CArchiveException` nesnenin *neden* değerini nesnede depolar.

```
CArchiveException(
    int cause = CArchiveException::none,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Parametreler

*sağlamak*<br/>
Özel durumun nedenini gösteren numaralandırılmış tür değişkeni. Numaralandırıcıların bir listesi için [m_cause](#m_cause) veri üyesine bakın.

*lpszArchiveName*<br/>
Özel duruma neden olan nesnenin adını içeren bir dizeye işaret eder `CArchive` .

### <a name="remarks"></a>Açıklamalar

`CArchiveException`Yığın üzerinde bir nesne oluşturabilir ve kendiniz oluşturabilir ya da genel Işlevin [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) işlemesini sağlayabilirsiniz.

Bu oluşturucuyu doğrudan kullanmayın; Bunun yerine, genel işlevini çağırın `AfxThrowArchiveException` .

## <a name="carchiveexceptionm_cause"></a><a name="m_cause"></a> CArchiveException:: m_cause

Özel durumun nedenini belirtir.

```
int m_cause;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi, türünde ortak bir değişkendir **`int`** . Değerleri, numaralandırılmış bir tür tarafından tanımlanır `CArchiveException` . Numaralandırıcılar ve anlamları aşağıdaki gibidir:

- `CArchiveException::none` Hata oluşmadı.

- `CArchiveException::genericException` Belirtilmeyen hata.

- `CArchiveException::readOnly` Yükleme için açılmış bir arşive yazmaya çalışıldı.

- `CArchiveException::endOfFile` Bir nesne okunurken dosyanın sonuna erişildi.

- `CArchiveException::writeOnly` Depolanması için açılan bir arşivden okunmaya çalışıldı.

- `CArchiveException::badIndex` Geçersiz dosya biçimi.

- `CArchiveException::badClass` Yanlış türdeki bir nesneye bir nesne okunmaya çalışıldı.

- `CArchiveException::badSchema` Sınıfının farklı bir sürümüne sahip bir nesne okunmaya çalışıldı.

    > [!NOTE]
    >  Bu `CArchiveException` neden Numaralandırıcılar `CFileException` neden numaralandırıcılardan farklıdır.

    > [!NOTE]
    > `CArchiveException::generic` kullanım dışıdır. Bunun yerine `genericException` kullanın. **Genel** bir uygulamada kullanılırsa ve/clr ile derlense, şifre çöz kolay olmayan sözdizimi hataları olur.

## <a name="carchiveexceptionm_strfilename"></a><a name="m_strfilename"></a> CArchiveException:: m_strFileName

Bu özel durum koşulunun dosya adını belirtir.

```
CString m_strFileName;
```

## <a name="see-also"></a>Ayrıca bkz.

[CException sınıfı](../../mfc/reference/cexception-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CArchive sınıfı](../../mfc/reference/carchive-class.md)<br/>
[AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)<br/>
[Özel durum Işleme](../../mfc/reference/exception-processing.md)
