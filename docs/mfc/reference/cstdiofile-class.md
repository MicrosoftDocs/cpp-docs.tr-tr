---
title: CStdioFile sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: fd42934107591905a1bbc273ee9eec4b37e58ea7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258794"
---
# <a name="cstdiofile-class"></a>CStdioFile sınıfı

Çalışma zamanı işlevi tarafından çalıştırıldığında C çalışma zamanı Akış dosyasını temsil eden [fopen](../../c-runtime-library/reference/fopen-wfopen.md).

## <a name="syntax"></a>Sözdizimi

```
class CStdioFile : public CFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CStdioFile::CStdioFile](#cstdiofile)|Oluşturur bir `CStdioFile` nesne yolu veya dosya işaretçisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CStdioFile::Open](#open)|Fazla Yüklendi. Açık varsayılan ile kullanılmak üzere tasarlanmıştır `CStdioFile` Oluşturucusu (geçersiz kılmaları [CFile::Open](../../mfc/reference/cfile-class.md#open)).|
|[CStdioFile::ReadString](#readstring)|Tek satırlık metin okur.|
|[CStdioFile::Seek](#seek)|Geçerli dosya işaretçisini yerleştirir.|
|[CStdioFile::WriteString](#writestring)|Tek satırlık metin yazar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CStdioFile::m_pStream](#m_pstream)|Açık bir dosyaya bir işaretçi içerir.|

## <a name="remarks"></a>Açıklamalar

Stream dosyaları ara belleğe alınır ve metin modunda (varsayılan) veya İkili modda açılabilir.

Metin modunda, satır başı satır besleme çiftleri için özel işleme sağlar. Yeni bir satır yazdığınızda metin modunda (0x0A) karakter `CStdioFile` nesnesi, bayt çifti (0x0D, 0x0A) dosyasına gönderilir. Okurken, bayt çifti (0x0D, 0x0A) tek 0x0A bayta dönüştürülür.

[CFile](../../mfc/reference/cfile-class.md) işlevleri [yinelenen](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), ve [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) desteklenmez `CStdioFile`.

Bu işlevler çağırırsanız bir `CStdioFile`, erişmenizi sağlayacak bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Kullanma hakkında daha fazla bilgi için `CStdioFile`, makalelere göz atın [MFC'deki dosyalar](../../mfc/files-in-mfc.md) ve [dosya işleme](../../c-runtime-library/file-handling.md) içinde *çalışma zamanı kitaplığı başvurusu*.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CStdioFile`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="cstdiofile"></a>  CStdioFile::CStdioFile

Oluşturur ve başlatır bir `CStdioFile` nesne.

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
C çalışma zamanı işlevine bir çağrı tarafından döndürülen dosya işaretçisini belirtir [fopen](../../c-runtime-library/reference/fopen-wfopen.md).

*lpszFileName*<br/>
İstenen dosya yolu bir dize belirtir. Göreli veya mutlak yol olabilir.

*nOpenFlags*<br/>
Dosya oluşturma, dosya paylaşımı ve dosya erişim modları için seçenekler belirtir. Bit düzeyinde OR kullanarak birden fazla seçenek belirtebilirsiniz ( **|** ) işleci.

Bir dosya erişim modu seçeneği gereklidir; Diğer modları isteğe bağlıdır. Bkz: [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) modu seçenekleri ve diğer bayraklar listesi. MFC sürüm 3.0 ve sonraki, paylaşım bayrakları izin verilir.

*pTM*<br/>
CAtlTransactionManager nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu, bir dosyaya eklemez `CStdioFile` nesne. Bu oluşturucuyu kullanırken, kullanmalısınız `CStdioFile::Open` bir dosyasını açın ve ekler için yöntem `CStdioFile` nesne.

Bir açık dosya akışı tek parametre oluşturucuya iliştirir `CStdioFile` nesne. İşaretçi değerler önceden tanımlanmış giriş/çıkış dosya işaretçileri izin *stdin*, *stdout*, veya *stderr*.

İki parametre Oluşturucu bir `CStdioFile` nesnesini ve karşılık gelen dosyayı ile verilen yol açar.

NULL ya da geçirirseniz *pOpenStream* veya *lpszFileName*, oluşturucu oluşturur bir `CInvalidArgException*`.

Dosya açılamadı veya olamaz, oluşturucu oluşturur bir `CFileException*`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#37](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]

##  <a name="m_pstream"></a>  CStdioFile::m_pStream

`m_pStream` C çalışma zamanı işlevi tarafından döndürülen veri üyesi olan bir açık dosya işaretçisi `fopen`.

```
FILE* m_pStream;
```

### <a name="remarks"></a>Açıklamalar

Dosya hiçbir zaman açılmış veya kapatılmış olan, NULL olur.

##  <a name="open"></a>  CStdioFile::Open

Fazla Yüklendi. Açık varsayılan ile kullanılmak üzere tasarlanmıştır `CStdioFile` Oluşturucusu.

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
İstenen dosya yolu bir dize. Göreli veya mutlak yol olabilir.

*nOpenFlags*<br/>
Paylaşım ve erişim modu. Dosyayı açarken gerçekleştirilecek eylemi belirtir. Seçenekler bit düzeyinde OR kullanarak birleştirebilir (&#124;) işleci. Bir erişim izni ve bir paylaşım seçeneği gereklidir; modeCreate ve modeNoInherit modları isteğe bağlıdır.

*pError*<br/>
Başarısız bir işlemin durumunu alacak varolan bir dosyanın özel durum nesnesine bir işaretçi.

*pTM*<br/>
İşaretçi bir `CAtlTransactionManager` nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="readstring"></a>  CStdioFile::ReadString

Bir sınır en fazla arabellek içine metin verileri okur *nMax*ilişkili dosyasından -1 karakter `CStdioFile` nesne.

```
virtual LPTSTR ReadString(
    LPTSTR lpsz,
    UINT nMax);

virtual BOOL ReadString(CString& rString);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Bir metin null ile sonlandırılmış dize alacak bir kullanıcı tarafından sağlanan arabellek için işaretçi belirtir.

*nMax*<br/>
Sondaki null karakter sayılmaz karakterleri okumak için en yüksek sayısını belirtir.

*rString*<br/>
Bir başvuru bir `CString` işlevi döndüğünde dizeyi içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Metin verileri içeren arabellek için işaretçi. Dosya sonu herhangi bir veri okumadan ulaştıysanız NULL; veya, boolean, dosya sonu ise FALSE herhangi bir veri okumadan ulaşıldı.

### <a name="remarks"></a>Açıklamalar

Okuma ilk yeni satır karakteri tarafından durduruldu. Bu durumda, daha az ise *nMax*-1 karakter okumak, arabellekteki yeni satır karakteri depolanır. Null karakteri ('\0'), her iki durumda da eklenir.

[CFile::Read](../../mfc/reference/cfile-class.md#read) metin modunda girdi, ancak değil sonlandırmak için bir satır başı satır besleme çiftine de kullanılabilir.

> [!NOTE]
>  `CString` Bu işlevin sürümünü kaldırır `'\n'` varsa; LPTSTR sürümü yok.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#38](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]

##  <a name="seek"></a>  CStdioFile::Seek

İşaretçi önceden açılmış bir dosyaya yeniden konumlandırır.

```
virtual ULONGLONG Seek(
    LONGLONG lOff,
    UINT nFrom);
```

### <a name="parameters"></a>Parametreler

*lOff*<br/>
İşaretçiyi bayt sayısı.

*nFrom*<br/>
İşaretçi taşıma modu. Aşağıdaki değerlerden biri olmalıdır:

- `CFile::begin`: Dosya işaretçiyi *lOff* dosyanın başından itibaren bayt iletin.

- `CFile::current`: Dosya işaretçiyi *lOff* dosyasındaki geçerli konumdan bayt.

- `CFile::end`: Dosya işaretçiyi *lOff* dosyasının sonuna gelen baytlar. Unutmayın *lOff* gerekir olması negatif mevcut aranacak dosya; pozitif değerleri, dosyanın sonundan arama.

### <a name="return-value"></a>Dönüş Değeri

İstenen konumu yasal, ise `Seek` dosyanın başından itibaren yeni bayt uzaklığı döndürür. Aksi takdirde, dönüş değeri tanımsızdır ve `CFileException` nesnesi oluşturulur.

### <a name="remarks"></a>Açıklamalar

`Seek` İşlevi erişme izni verir rastgele bir dosyanın içeriğini hareket ettirerek işaretçinin belirtilen bir miktarı mutlak veya göreceli olarak. Veri yok, arama sırasında gerçekten okuyun. İstenen konumu, dosya boyutundan büyükse, dosya uzunluğu o konuma genişletilir ve hiçbir özel durum oluşturulur.

Bir dosya açıldığında, dosya işaretçisini uzaklığı 0 ' dosyasının başına yerleştirilir.

Bu uygulaması `Seek` çalışma zamanı kitaplığı (CRT) işlevine dayalı `fseek`. Kullanımı ve birkaç sınırları vardır `Seek` akışlarında metin modunda açılır. Daha fazla bilgi için [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md).

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `Seek` işaretçiyi başından 1000 bayt `cfile` dosya. Unutmayın `Seek` sonradan çağırmanız gerekir böylece veri okumaz [CStdioFile::ReadString](#readstring) verileri okumak için.

[!code-cpp[NVC_MFCFiles#39](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]

##  <a name="writestring"></a>  CStdioFile::WriteString

Veri arabellek ile ilişkili bir dosyaya yazar `CStdioFile` nesne.

```
virtual void WriteString(LPCTSTR lpsz);
```

### <a name="parameters"></a>Parametreler

*lpsz*<br/>
Null ile sonlandırılmış bir dize içeren arabellek için işaretçi belirtir.

### <a name="remarks"></a>Açıklamalar

Sondaki boş karakter ( `\0`) dosyasına yazılmaz. Bu yöntem, yeni satır karakterleri Yazar *lpsz* dosyaya bir satır başı/satır besleme çift olarak.

Bir dosyaya, kullanmak null ile sonlandırılmış değil veri yazmak istiyorsanız `CStdioFile::Write` veya [CFile::Write](../../mfc/reference/cfile-class.md#write).

Bu yöntem bir `CInvalidArgException*` NULL belirtirseniz *lpsz* parametresi.

Bu yöntem bir `CFileException*` yanıt olarak dosya sistemi hataları.

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
