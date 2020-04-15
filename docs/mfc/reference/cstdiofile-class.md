---
title: CStdioFile Sınıfı
ms.date: 08/29/2019
f1_keywords:
- CStdioFile
- AFX/CStdioFile
- AFX/CStdioFile::CStdioFile
- AFX/CStdioFile::Open
- AFX/CStdioFile::ReadString
- AFX/CStdioFile::Seek
- AFX/CStdioFile::WriteString
- AFX/CStdioFile::m_pStream
helpviewer_keywords:
- CStdioFile [MFC], CStdioFile
- CStdioFile [MFC], Open
- CStdioFile [MFC], ReadString
- CStdioFile [MFC], Seek
- CStdioFile [MFC], WriteString
- CStdioFile [MFC], m_pStream
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
ms.openlocfilehash: 80ee65aa339a38b3d8434bc4c7cb977e263f037b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366009"
---
# <a name="cstdiofile-class"></a>CStdioFile Sınıfı

Çalışma zamanı işlevi [fopen](../../c-runtime-library/reference/fopen-wfopen.md)tarafından açılan c çalışma zamanı akış dosyasını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CStdioFile : public CFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CStdioFile::CStdioFile](#cstdiofile)|Bir yol `CStdioFile` veya dosya işaretçisinden bir nesne oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CStdioFile::Aç](#open)|Fazla Yüklendi. Açık varsayılan `CStdioFile` oluşturucu ile kullanılmak üzere tasarlanmıştır [(Overrides CFile::Open).](../../mfc/reference/cfile-class.md#open)|
|[CStdioFile::ReadString](#readstring)|Tek bir metin satırı okur.|
|[CStdioFile::Ara](#seek)|Geçerli dosya işaretçisini konumlandırın.|
|[CStdioFile::WriteString](#writestring)|Tek bir metin satırı yazar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CStdioFile::m_pStream](#m_pstream)|Açık bir dosyaiçin işaretçi içerir.|

## <a name="remarks"></a>Açıklamalar

Akış dosyaları arabelleğe alınır ve metin modunda (varsayılan) veya ikili modda açılabilir.

Metin modu, satır başı besleme çiftleri için özel işleme sağlar. Metin modu `CStdioFile` nesnesine satır akışı (newline) karakteri (0x0A) yazdığınızda, bayt çifti (0x0D, 0x0A) dosyaya gönderilir. Okuduğunuz zaman, bayt çifti (0x0D, 0x0A) tek bir 0x0A bayt çevrilmiştir.

[CFile](../../mfc/reference/cfile-class.md) işlevleri [Yinelenen](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange)ve [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) `CStdioFile`için desteklenmez.

Bu işlevleri bir `CStdioFile` [cnotsupportedException](../../mfc/reference/cnotsupportedexception-class.md)alırsınız.

Kullanma `CStdioFile`hakkında daha fazla bilgi için, *Çalışma Zamanı Kitaplığı Başvurusu'nda* [MFC'deki](../../mfc/files-in-mfc.md) dosyalar adabına ve [Dosya İşleme'ye](../../c-runtime-library/file-handling.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfile](../../mfc/reference/cfile-class.md)

`CStdioFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cstdiofilecstdiofile"></a><a name="cstdiofile"></a>CStdioFile::CStdioFile

Bir `CStdioFile` nesne yi inşa eder ve başharfe ait hale raz.

```
CStdioFile();
CStdioFile(CAtlTransactionManager* pTM);
CStdioFile(FILE* pOpenStream);

CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags);

CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Parametreler

*pOpenStream*<br/>
C çalışma zamanı işlevi [fopen](../../c-runtime-library/reference/fopen-wfopen.md)bir çağrı tarafından döndürülen dosya işaretçisi belirtir.

*lpszFileName*<br/>
İstenilen dosyaya giden yol olan bir dize belirtir. Yol göreceli veya mutlak olabilir.

*nOpen Bayraklar*<br/>
Dosya oluşturma, dosya paylaşımı ve dosya erişim modları için seçenekleri belirtir. Bitwise OR ( **|** ) işleci kullanarak birden çok seçenek belirtebilirsiniz.

Bir dosya erişim modu seçeneği gereklidir; diğer modlar isteğe bağlıdır. [Bkz. CFile::CFile](../../mfc/reference/cfile-class.md#cfile) modu seçenekleri ve diğer bayrakların listesi için. MFC sürüm 3.0 ve sonraki sürümlerde, paylaşım bayraklarına izin verilir.

*pTM*<br/>
CAtlTransactionManager nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Varsayılan oluşturucu `CStdioFile` nesneye dosya eklemez. Bu oluşturucuyu kullanırken, `CStdioFile::Open` bir dosyayı açmak ve `CStdioFile` nesneye eklemek için yöntemi kullanmanız gerekir.

Tek parametre oluşturucu `CStdioFile` nesneye açık bir dosya akışı bağlar. İzin verilen işaretçi değerleri önceden tanımlanmış giriş/çıkış dosya işaretçileri *stdin,* *stdout*veya *stderr*içerir.

İki parametre oluşturucu bir `CStdioFile` nesne oluşturur ve verilen yol ile ilgili dosyayı açar.

Ya *pOpenStream* veya *lpszFileName*için NULL geçerseniz, `CInvalidArgException*`yapıcı atar .

Dosya açılamıyorsa veya oluşturulamıyorsa, oluşturucu `CFileException*`bir .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]

## <a name="cstdiofilem_pstream"></a><a name="m_pstream"></a>CStdioFile::m_pStream

Veri `m_pStream` üyesi, C çalışma zamanı işlevi `fopen`tarafından döndürülen açık bir dosyanın işaretçisidir.

```
FILE* m_pStream;
```

### <a name="remarks"></a>Açıklamalar

Dosya hiç açılmamışsa veya kapatılmışsa NULL'dur.

## <a name="cstdiofileopen"></a><a name="open"></a>CStdioFile::Aç

Fazla Yüklendi. Açık varsayılan `CStdioFile` oluşturucu ile kullanılmak üzere tasarlanmıştır.

```
virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM,
    CFileException* pError = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
İstenilen dosyaya giden yol olan dize. Yol göreceli veya mutlak olabilir.

*nOpen Bayraklar*<br/>
Paylaşım ve erişim modu. Dosyayı açarken yapılacak eylemi belirtir. Bitwise-OR (&#124;) işleci kullanarak seçenekleri birleştirebilirsiniz. Bir erişim izni ve bir paylaşım seçeneği gereklidir; modeCreate ve modeNoInherit modları isteğe bağlıdır.

*pHata*<br/>
Başarısız bir işlem durumunu alacak varolan bir dosya özel durum nesnesi için bir işaretçi.

*pTM*<br/>
Bir `CAtlTransactionManager` nesneye işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cstdiofilereadstring"></a><a name="readstring"></a>CStdioFile::ReadString

`CStdioFile` Nesneyle ilişkili dosyadan metin verilerini *nMax*-1 karakter sınırına kadar bir arabellek halinde okur.

```
virtual LPTSTR ReadString(
    LPTSTR lpsz,
    UINT nMax);

virtual BOOL ReadString(CString& rString);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Null-sonlandırılan metin dizesini alacak kullanıcı tarafından sağlanan arabellek için bir işaretçi belirtir.

*nMax*<br/>
Null karakterini sonlandırmayı saymazsak, okunacak maksimum karakter sayısını belirtir.

*rString*<br/>
İşlev döndüğünde `CString` dizeyi içerecek bir nesneye başvuru.

### <a name="return-value"></a>Dönüş Değeri

Metin verilerini içeren arabelleğe işaretçi. Dosya sonu herhangi bir veri okumadan ulaşıldıysa NULL; veya boolean ise, dosya sonu herhangi bir veri okumadan ulaşıldı eğer FALSE.

### <a name="remarks"></a>Açıklamalar

Okuma ilk yeni satır karakteri tarafından durdurulur. Bu durumda, *nMax*-1 karakterden daha az karakter okunduysa, arabellekte yeni bir satır karakteri depolanır. Her iki durumda da null karakter ('\0') eklenir.

[CFile::Read](../../mfc/reference/cfile-class.md#read) metin modu girişi için de kullanılabilir, ancak bir satır satır satır besleme çifti üzerinde sona ermez.

> [!NOTE]
> Bu `CString` işlevin sürümü `'\n'` varsa varsa kaldırır; LPTSTR sürümü yok.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]

## <a name="cstdiofileseek"></a><a name="seek"></a>CStdioFile::Ara

İşaretçiyi daha önce açılmış bir dosyada yeniden konumlandırın.

```
virtual ULONGLONG Seek(
    LONGLONG lOff,
    UINT nFrom);
```

### <a name="parameters"></a>Parametreler

*lOff*<br/>
İşaretçiyi taşımak için bayt sayısı.

*nKaynak*<br/>
İşaretçi hareket modu. Aşağıdaki değerlerden biri olmalıdır:

- `CFile::begin`: Dosya işaretçisi *lOff* baytlarını dosyanın başından ileri taşıyın.

- `CFile::current`: Dosya işaretçisi *lOff* baytlarını dosyadaki geçerli konumdan taşıyın.

- `CFile::end`: Dosya işaretçisi *lOff* baytlarını dosyanın sonundan taşıyın. *lOff'un* varolan dosyayı aramak için negatif olması gerektiğini unutmayın; pozitif değerler dosyanın sonuna kadar arayacaktır.

### <a name="return-value"></a>Dönüş Değeri

İstenen pozisyon yasalsa, `Seek` dosyanın başından itibaren yeni bayt mahsulü iade edilir. Aksi takdirde, iade değeri tanımsız ve bir `CFileException` nesne atılır.

### <a name="remarks"></a>Açıklamalar

İşlev, `Seek` işaretçiyi kesinlikle veya göreli olarak belirli bir miktarda taşıyarak dosyanın içeriğine rasgele erişime izin verir. Arama sırasında hiçbir veri aslında okunmaz. İstenen konum dosyanın boyutundan büyükse, dosya uzunluğu bu konuma uzatılır ve özel durum atılmaz.

Bir dosya açıldığında, dosya işaretçisi dosyanın başlangıcı olan ofset 0'da konumlandırılır.

Bu uygulama `Seek` Run-Time Library (CRT) işlevini `fseek`temel almaktadır. Metin modunda açılan akışlarda `Seek` kullanımıiçin çeşitli sınırlar vardır. Daha fazla bilgi için bkz: [fseek, _fseeki64.](../../c-runtime-library/reference/fseek-fseeki64.md)

### <a name="example"></a>Örnek

Aşağıdaki örnek, işaretçi1000 baytı dosyanın başından taşımak `cfile` için nasıl kullanılacağını `Seek` gösterir. Verileri `Seek` okumadığını unutmayın, bu nedenle daha sonra verileri okumak için [CStdioFile::ReadString'i](#readstring) aramanız gerekir.

[!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]

## <a name="cstdiofilewritestring"></a><a name="writestring"></a>CStdioFile::WriteString

`CStdioFile` Arabellekten nesneyle ilişkili dosyaya veri yazar.

```
virtual void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Null-sonlandırılan dize içeren bir arabellek için işaretçi belirtir.

### <a name="remarks"></a>Açıklamalar

Sonlandırıcı null karakter ( `\0`) dosyaya yazılmadı. Bu yöntem, *lpsz'deki* yeni satır karakterlerini bir satır satır satır besleme çifti olarak dosyaya yazar.

Bir dosyaya geçersiz kılınmayan verileri yazmak istiyorsanız, `CStdioFile::Write` kullanın veya [CFile::Yaz.](../../mfc/reference/cfile-class.md#write)

Bu `CInvalidArgException*` *yöntem, lpsz* parametresi için NULL belirtirseniz bir atar.

Bu yöntem, `CFileException*` dosya sistemi hatalarıyanıt bir atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#40](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CFile Sınıfı](../../mfc/reference/cfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFile Sınıfı](../../mfc/reference/cfile-class.md)<br/>
[CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)<br/>
[CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)<br/>
[CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)<br/>
[CNotSupportedException Sınıfı](../../mfc/reference/cnotsupportedexception-class.md)
