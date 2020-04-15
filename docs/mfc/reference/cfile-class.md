---
title: CFile Sınıfı
ms.date: 06/12/2018
f1_keywords:
- CFile
- AFX/CFile
- AFX/CFile::CFile
- AFX/CFile::Abort
- AFX/CFile::Close
- AFX/CFile::Duplicate
- AFX/CFile::Flush
- AFX/CFile::GetFileName
- AFX/CFile::GetFilePath
- AFX/CFile::GetFileTitle
- AFX/CFile::GetLength
- AFX/CFile::GetPosition
- AFX/CFile::GetStatus
- AFX/CFile::LockRange
- AFX/CFile::Open
- AFX/CFile::Read
- AFX/CFile::Remove
- AFX/CFile::Rename
- AFX/CFile::Seek
- AFX/CFile::SeekToBegin
- AFX/CFile::SeekToEnd
- AFX/CFile::SetFilePath
- AFX/CFile::SetLength
- AFX/CFile::SetStatus
- AFX/CFile::UnlockRange
- AFX/CFile::Write
- AFX/CFile::hFileNull
- AFX/CFile::m_hFile
- AFX/CFile::m_pTM
helpviewer_keywords:
- CFile [MFC], CFile
- CFile [MFC], Abort
- CFile [MFC], Close
- CFile [MFC], Duplicate
- CFile [MFC], Flush
- CFile [MFC], GetFileName
- CFile [MFC], GetFilePath
- CFile [MFC], GetFileTitle
- CFile [MFC], GetLength
- CFile [MFC], GetPosition
- CFile [MFC], GetStatus
- CFile [MFC], LockRange
- CFile [MFC], Open
- CFile [MFC], Read
- CFile [MFC], Remove
- CFile [MFC], Rename
- CFile [MFC], Seek
- CFile [MFC], SeekToBegin
- CFile [MFC], SeekToEnd
- CFile [MFC], SetFilePath
- CFile [MFC], SetLength
- CFile [MFC], SetStatus
- CFile [MFC], UnlockRange
- CFile [MFC], Write
- CFile [MFC], hFileNull
- CFile [MFC], m_hFile
- CFile [MFC], m_pTM
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
ms.openlocfilehash: 4ba37d481db73fb0556659ede267b3474c3f32f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373915"
---
# <a name="cfile-class"></a>CFile Sınıfı

Microsoft Hazırlık Sınıfı dosya sınıfları için taban sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CFile : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFile::CFile](#cfile)|Bir yol `CFile` veya dosya tutamacından bir nesne oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFile::İptal](#abort)|Tüm uyarıları ve hataları yoksayarak bir dosyayı kapatır.|
|[CFile::Kapat](#close)|Bir dosyayı kapatır ve nesneyi siler.|
|[CFile::Duplicate](#duplicate)|Bu dosyayı temel alan yinelenen bir nesne oluşturuyor.|
|[CFile::Flush](#flush)|Henüz yazılmayı niçin temize çıkar.|
|[Dosya::GetFileName](#getfilename)|Seçili dosyanın dosya adını alır.|
|[CFile::GetFilePath](#getfilepath)|Seçili dosyanın tam dosya yolunu alır.|
|[CFile::GetFileTitle](#getfiletitle)|Seçili dosyanın başlığını alır.|
|[CFile::GetLength](#getlength)|Dosyanın uzunluğunu alır.|
|[CFile::GetPosition](#getposition)|Geçerli dosya işaretçisini alır.|
|[CFile::GetStatus](#getstatus)|Açık dosyanın durumunu alır veya statik sürümde, belirtilen dosyanın durumunu alır (statik, sanal işlev).|
|[CFile::LockRange](#lockrange)|Bir dosyada bayt aralığını kilitler.|
|[CFile::Aç](#open)|Hata sınama seçeneği olan bir dosyayı güvenle açar.|
|[CFile::Oku](#read)|Geçerli dosya konumundaki bir dosyadan gelen verileri okur (arabelleğe alma) sağlar.|
|[CFile::Kaldır](#remove)|Belirtilen dosyayı (statik işlev) siler.|
|[CFile::Yeniden Adlandır](#rename)|Belirtilen dosyayı (statik işlev) yeniden adlandırır.|
|[CFile::Seek](#seek)|Geçerli dosya işaretçisini konumlandırın.|
|[CFile::SeektoBegin](#seektobegin)|Geçerli dosya işaretçisini dosyanın başında konumlandırın.|
|[CFile::Seektoend](#seektoend)|Geçerli dosya işaretçisini dosyanın sonunda konumlandırın.|
|[Dosya::SetFilePath](#setfilepath)|Seçili dosyanın tam dosya yolunu ayarlar.|
|[CFile::Setlength](#setlength)|Dosyanın uzunluğunu değiştirir.|
|[CFile::SetStatus](#setstatus)|Belirtilen dosyanın durumunu (statik, sanal işlev) ayarlar.|
|[CFile::UnlockRange](#unlockrange)|Dosyadaki bayt aralığının kilidini açar.|
|[CFile::Yaz](#write)|Dosyadaki verileri geçerli dosya konumuna yazar (arabelleğe alma) yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CFile::operatör HANDLE](#operator_handle)|Bir `CFile` nesneye tutamak.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CFile::hFileNull](#hfilenull)|Nesnenin `CFile` geçerli bir tutamacı olup olmadığını belirler.|
|[CFile::m_hFile](#m_hfile)|Genellikle işletim sistemi dosya tutamacını içerir.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CFile::m_pTM](#m_ptm)|İtiraz `CAtlTransactionManager` için işaretçi.|

## <a name="remarks"></a>Açıklamalar

Doğrudan arabelleğe alamayan, ikili disk giriş/çıkış hizmetleri sağlar ve dolaylı olarak türetilmiş sınıfları aracılığıyla metin dosyalarını ve bellek dosyalarını destekler. `CFile`Microsoft Foundation Class `CArchive` nesnelerinin serileştirilmesini desteklemek için sınıfla birlikte çalışır.

Bu sınıf ve türetilmiş sınıfları arasındaki hiyerarşik ilişki, programınızın çok `CFile` biçimli arabirim aracılığıyla tüm dosya nesneleri üzerinde çalışmasına olanak tanır. Örneğin, bir bellek dosyası bir disk dosyası gibi olur.

Genel `CFile` amaçlı disk G/Ç için kullanımı ve türetilmiş sınıfları. Bir `ofstream` disk `iostream` dosyasına gönderilen biçimlendirilmiş metin için kullanın veya diğer Microsoft sınıflarını kullanın.

Normalde, bir disk dosyası inşaat `CFile` otomatik olarak açılır ve imha kapalı. Statik üye işlevler, dosyayı açmadan dosyanın durumunu sorgulamanızı sağlar.

Kullanma `CFile`hakkında daha fazla bilgi için, *Çalışma Zamanı Kitaplığı Başvurusu'nda* [MFC'deki](../../mfc/files-in-mfc.md) dosyalar adabına ve [Dosya İşleme'ye](../../c-runtime-library/file-handling.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cfileabort"></a><a name="abort"></a>CFile::İptal

Bu nesneyle ilişkili dosyayı kapatır ve dosyayı okuma veya yazma için kullanılamaz hale getirir.

```
virtual void Abort();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi yok etmeden önce dosyayı kapatmadıysanız, yıkıcı dosyayı sizin için kapatır.

Özel durumları işlerken, `CFile::Abort` `CFile::Close` iki önemli şekilde farklıdır. İlk olarak, `Abort` işlev hatalara özel bir özel durum atmayacak, çünkü hatalar . `Abort` İkinci `Abort` olarak, dosya açılmamışsa veya daha önce kapatılmışsa **Assert** olmaz.

Nesneyi `CFile` yığına ayırmak için **yeni** bir şey kullandıysanız, dosyayı kapattıktan sonra silmeniz gerekir. `Abort`için `m_hFile` `CFile::hFileNull`ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]

## <a name="cfilecfile"></a><a name="cfile"></a>CFile::CFile

Bir `CFile` nesne yi inşa eder ve başharfe ait hale raz.

```
CFile();
CFile(CAtlTransactionManager* pTM);
CFile(HANDLE hFile);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags);

CFile(
LPCTSTR lpszFileName,
UINT nOpenFlags,
CAtlTransactionManager* pTM);
```

### <a name="parameters"></a>Parametreler

*hFile*<br/>
Nesneye iliştirecek `CFile` bir dosyanın tutamacı.

*lpszFileName*<br/>
`CFile` Nesneye eklemek için bir dosyanın göreli veya tam yolu.

*nOpen Bayraklar*<br/>
Belirtilen dosya için dosya erişim seçeneklerinin Bitwise birleşimi (OR). Olası seçenekler için Açıklamalar bölümüne bakın.

*pTM*<br/>
CAtlTransactionManager nesnesine işaretçi

### <a name="remarks"></a>Açıklamalar

Aşağıdaki beş tabloda *nOpenFlags* parametresi için olası seçenekler listeleilmektedir.

Aşağıdaki dosya erişim modu seçeneklerinden yalnızca birini seçin. Varsayılan dosya erişim `CFile::modeRead`modu, yalnızca okunur.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::modeRead`|İstekler yalnızca erişim okunur.|
|`CFile::modeWrite`|İstekler yalnızca erişim yazmak.|
|`CFile::modeReadWrite`|İstekler erişim okuma ve yazma.|

Aşağıdaki karakter modu seçeneklerinden birini seçin.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::typeBinary`|İkili modu ayarlar (yalnızca türemiş sınıflarda kullanılır).|
|`CFile::typeText`|Satır başı satır besleme çiftleri için özel işleme ile metin modunu ayarlar (yalnızca türemiş sınıflarda kullanılır).|
|`CFile::typeUnicode`|Unicode modunu ayarlar (yalnızca türemiş sınıflarda kullanılır). Uygulama Unicode yapılandırmasında oluşturulunca metin Dosyaya Unicode biçiminde yazılır. Dosyaya hiçbir BOM yazılmadı.|

Aşağıdaki dosya paylaşımı modu seçeneklerinden yalnızca birini seçin. Varsayılan dosya paylaşım `CFile::shareExclusive`modu, özeldir.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::shareDenyNone`|Paylaşım kısıtlaması yok.|
|`CFile::shareDenyRead`|Diğer lerini okumayı reddediyor.|
|`CFile::shareDenyWrite`|İnkârlar diğerlerine erişim yazmayı reddediyor.|
|`CFile::shareExclusive`|Diğerlerine erişim okuma ve yazmayı reddediyor.|

Aşağıdaki dosya oluşturma modu seçeneklerinin ilkini veya her ikisini seçin. Varsayılan oluşturma `CFile::modeNoTruncate`modu, varolan açık.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::modeCreate`|Dosya yoksa yeni bir dosya oluşturur. Dosya zaten varsa, üzerine yazılır ve başlangıçta sıfır uzunluğa ayarlanır.|
|`CFile::modeNoTruncate`|Dosya yoksa yeni bir dosya oluşturur; aksi takdirde, dosya zaten varsa, `CFile` nesneye iliştirilir.|

Açıklandığı gibi aşağıdaki dosya önbelleğe alma seçeneklerini seçin. Varsayılan olarak, sistem seçenek olarak kullanılamayan genel amaçlı bir önbelleğe alma düzeni kullanır.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::osNoBuffer`|Sistem dosya için ara önbellek kullanmaz. Bu seçenek aşağıdaki 2 seçeneği iptal eder.|
|`CFile::osRandomAccess`|Dosya önbelleği rasgele erişim için en iyi duruma getirilmiş. Hem bu seçeneği hem de sıralı tarama seçeneğini kullanmayın.|
|`CFile::osSequentialScan`|Dosya önbelleği sıralı erişim için en iyi duruma getirilmiş. Hem bu seçeneği hem de rasgele erişim seçeneğini kullanmayın.|
|`CFile::osWriteThrough`|Yazma işlemleri gecikmeden yapılır.|

Dosya tanıtıcısının devralınmasını önlemek için aşağıdaki güvenlik seçeneğini belirleyin. Varsayılan olarak, herhangi bir yeni alt işlemler dosya tutamacını kullanabilirsiniz.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::modeNoInherit`|Alt işlemlerin dosya tutamacını kullanmasını engeller.|

Varsayılan oluşturucu üyeleri başlatılmasını sağlar, ancak `CFile` nesneye dosya eklemez. Bu oluşturucuyu kullandıktan sonra, bir dosyayı açmak ve nesneye `CFile` takmak için [CFile::Open](#open) yöntemini kullanın.

Bir parametreye sahip oluşturucu üyeleri başharfe alerler ve varolan bir dosyayı `CFile` nesneye bağlar.

İki parametreye sahip oluşturucu üyeleri açar ve belirtilen dosyayı açmaya çalışır. Bu oluşturucu belirtilen dosyayı başarıyla açarsa, `CFile` dosya nesneye eklenir; aksi takdirde, bu oluşturucu bir `CInvalidArgException` nesneye bir işaretçi atar. Özel durumların nasıl işleyeceğiniz hakkında daha fazla bilgi için [özel durumlara](../../mfc/exception-handling-in-mfc.md)bakın.

Bir `CFile` nesne belirtilen bir dosyayı başarıyla açarsa, `CFile` nesne yok edildiğinde bu dosyayı otomatik olarak kapatır; aksi takdirde, dosya nesneye `CFile` artık eklenmedikten sonra dosyayı açıkça kapatmanız gerekir.

### <a name="example"></a>Örnek

Aşağıdaki kod, bir `CFile`.

[!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]

## <a name="cfileclose"></a><a name="close"></a>CFile::Kapat

Bu nesneyle ilişkili dosyayı kapatır ve dosyayı okuma veya yazma için kullanılamaz hale getirir.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi yok etmeden önce dosyayı kapatmadıysanız, yıkıcı dosyayı sizin için kapatır.

Nesneyi `CFile` yığına ayırmak için **yeni** bir şey kullandıysanız, dosyayı kapattıktan sonra silmeniz gerekir. `Close`için `m_hFile` `CFile::hFileNull`ayarlar.

### <a name="example"></a>Örnek

CFile örneğine [bakın:CFile](#cfile).

## <a name="cfileduplicate"></a><a name="duplicate"></a>CFile::Duplicate

Belirli bir `CFile` dosya için yinelenen bir nesne oluşturuyor.

```
virtual CFile* Duplicate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yinelenen `CFile` bir nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev C çalışma zamanı işlevine `_dup`eşdeğerdir.

## <a name="cfileflush"></a><a name="flush"></a>CFile::Flush

Dosya arabelleğinde kalan tüm verileri dosyaya yazılmaya zorlar.

```
virtual void Flush();
```

### <a name="remarks"></a>Açıklamalar

Kullanımı, `Flush` arabelleklerin `CArchive` kızardığını garanti etmez. Arşiv kullanıyorsanız, [önce CArchive::Flush'ı](../../mfc/reference/carchive-class.md#flush) arayın.

### <a name="example"></a>Örnek

CFile örneğine [bakın:SetFilePath](#setfilepath).

## <a name="cfilegetfilename"></a><a name="getfilename"></a>Dosya::GetFileName

Belirtilen bir dosyanın adını almak için bu üye işlevi arayın.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosyanın adı.

### <a name="remarks"></a>Açıklamalar

Örneğin, dosya `GetFileName` `c:\windows\write\myfile.wri`hakkında kullanıcıya bir ileti oluşturmak için aradığınızda `myfile.wri`, dosya adı, döndürülür.

Ad da dahil olmak üzere dosyanın tüm yolunu döndürmek için [GetFilePath'i](#getfilepath)arayın. Dosyanın başlığını döndürmek `myfile`için ( ), [GetFileTitle'ı](#getfiletitle)arayın.

### <a name="example"></a>Örnek

Bu kod parçası SİsteMİ AÇAR. WINDOWS dizininizde INI dosyası. Bulunursa, örnek, Çıktı altında gösterildiği gibi adı, yolu ve başlığı yazdırır:

[!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]

## <a name="cfilegetfilepath"></a><a name="getfilepath"></a>CFile::GetFilePath

Belirtilen bir dosyanın tam yolunu almak için bu üye işlevi arayın.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dosyanın tam yolu.

### <a name="remarks"></a>Açıklamalar

Örneğin, dosya `GetFilePath` `c:\windows\write\myfile.wri`hakkında kullanıcıya bir ileti oluşturmak için aradığınızda `c:\windows\write\myfile.wri`, dosya yolu, döndürülür.

Sadece dosyanın adını döndürmek`myfile.wri`için ( ), [GetFileName'yi](#getfilename)arayın. Dosyanın başlığını döndürmek`myfile`için ( ), [GetFileTitle'ı](#getfiletitle)arayın.

### <a name="example"></a>Örnek

[GetFileName](#getfilename)için örneğe bakın.

## <a name="cfilegetfiletitle"></a><a name="getfiletitle"></a>CFile::GetFileTitle

Dosyanın dosya başlığını (görüntü adı) almak için bu üye işlevini arayın.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Temel dosyanın başlığı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, dosyanın başlığını almak için [GetFileTitle](/windows/win32/api/commdlg/nf-commdlg-getfiletitlew) çağırır. Yöntem başarılı olursa, dosya adını kullanıcıya görüntülemek için sistemin kullanacağı dizeyi döndürür. Aksi takdirde, yöntem, temel dosyanın dosya adını (dosya uzantısı dahil) almak için [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) çağırır. Bu, dosya uzantısının her zaman döndürülen dosya başlığı dizesinde yer olmadığı anlamına gelir. Daha fazla bilgi için Windows SDK'daki [GetFileTitle](/windows/win32/api/commdlg/nf-commdlg-getfiletitlew) ve [PathFindFileName'e](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) bakın.

Ad da dahil olmak üzere dosyanın tüm yolunu döndürmek için [GetFilePath'i](#getfilepath)arayın. Sadece dosyanın adını döndürmek için [GetFileName'yi](#getfilename)arayın.

### <a name="example"></a>Örnek

[GetFileName](#getfilename)için örneğe bakın.

## <a name="cfilegetlength"></a><a name="getlength"></a>CFile::GetLength

Dosyanın geçerli mantıksal uzunluğunu baytolarak alır.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosyanın uzunluğu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]

## <a name="cfilegetposition"></a><a name="getposition"></a>CFile::GetPosition

Daha sonraki aramalarda kullanılabilecek dosya işaretçisinin geçerli değerini `Seek`alır.

```
virtual ULONGLONG GetPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]

## <a name="cfilegetstatus"></a><a name="getstatus"></a>CFile::GetStatus

Bu yöntem, belirli bir nesne `CFile` örneği veya belirli bir dosya yolu ile ilgili durum bilgilerini alır.

```
BOOL GetStatus(CFileStatus& rStatus) const;

static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*rDurum*<br/>
Durum bilgilerini alacak kullanıcı `CFileStatus` tarafından sağlanan yapıya yapılan başvuru. Yapının `CFileStatus` aşağıdaki alanları vardır:

- `CTime m_ctime`Dosyanın oluşturulduğu tarih ve saat.

- `CTime m_mtime`Dosyanın en son değiştirilme tarihi ve saati.

- `CTime m_atime`Dosyaya en son okumak için erişilen tarih ve saat.

- `ULONGLONG m_size`DIR komutu tarafından bildirilen, baytlarda dosyanın mantıksal boyutu.

- `BYTE m_attribute`Dosyanın öznitelik bayt.

- `char m_szFullName[_MAX_PATH]`Windows karakter kümesindeki mutlak dosya adı.

*lpszFileName*<br/>
Windows karakter kümesinde istenen dosyaya giden yol olan dize. Yol göreceli veya mutlak olabilir veya bir ağ yolu adı içerebilir.

*pTM*<br/>
CAtlTransactionManager nesnesine işaretçi

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dosyanın durum bilgileri başarıyla elde edilirse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Statik olmayan sürümü, `GetStatus` verilen `CFile` nesneyle ilişkili açık dosyanın durum bilgilerini alır.  Statik sürümü, `GetStatus` dosyayı gerçekten açmadan belirli bir dosya yolundan dosya durumunu alır. Bu sürüm, bir dosyanın varlığını ve erişim haklarını sınanabilmek için yararlıdır.

Yapının `m_attribute` `CFileStatus` üyesi dosya öznitelik kümesini ifade eder. Sınıf, `CFile` dosya özniteliklerinin sembolik olarak belirtilen olması için **Öznitelik** numaralandırma türünü sağlar:

```
enum Attribute {
    normal =    0x00,
    readOnly =  0x01,
    hidden =    0x02,
    system =    0x04,
    volume =    0x08,
    directory = 0x10,
    archive =   0x20
    };
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#10](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_6.cpp)]

## <a name="cfilehfilenull"></a><a name="hfilenull"></a>CFile::hFileNull

Nesne için geçerli bir dosya tanıtıcısının `CFile` varlığını belirler.

```
static AFX_DATA const HANDLE hFileNull;
```

### <a name="remarks"></a>Açıklamalar

Bu sabit, nesnenin `CFile` geçerli bir dosya tanıtıcısı olup olmadığını belirlemek için kullanılır.

Aşağıdaki örnekbu işlemi gösterir:

[!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]

## <a name="cfilelockrange"></a><a name="lockrange"></a>CFile::LockRange

Açık bir dosyada bir dizi bayt kilitler ve dosya zaten kilitliyse özel durum oluşturur.

```
virtual void LockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Parametreler

*dwPos*<br/>
Kilitlemek için bayt aralığının başlangıcının bayt mahsulü.

*dwSay*<br/>
Kilitlemek için aralıktaki bayt sayısı.

### <a name="remarks"></a>Açıklamalar

Bir dosyadaki baytların kilitlenerek diğer işlemler tarafından bu baytlara erişimi engeller. Bir dosyanın birden fazla bölgesini kilitleyebilirsiniz, ancak çakışan bölgelere izin verilmez.

`UnlockRange` Üye işlevini kullanarak bölgenin kilidini açtığınızda, bayt aralığı daha önce kilitlenmiş olan bölgeye tam olarak karşılık vermelidir. İşlev `LockRange` bitişik bölgeleri birleştirmez. İki kilitli bölge bitişikse, her bölgenin ayrı ayrı kilidini açmanız gerekir.

> [!NOTE]
> Bu işlev `CMemFile`türetilmiş sınıf için kullanılamaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

## <a name="cfilem_hfile"></a><a name="m_hfile"></a>CFile::m_hFile

Açık bir dosya için işletim sistemi dosya tutamacını içerir.

```
HANDLE m_hFile;
```

### <a name="remarks"></a>Açıklamalar

`m_hFile`uint türü nde ortak bir değişkendir. Tutamacı `CFile::hFileNull`atanmamışsa, işletim sisteminden bağımsız boş dosya göstergesi içerir.

Üyenin `m_hFile` anlamı türemiş sınıfa bağlı olduğundan, kullanımı önerilmez. `m_hFile`sınıfın polimorfik olmayan kullanımını desteklemede kolaylık sağlamak için halka açık bir üye haline getirilir.

## <a name="cfilem_ptm"></a><a name="m_ptm"></a>CFile::m_pTM

Bir `CAtlTransactionManager` nesneye işaretçi.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cfileopen"></a><a name="open"></a>CFile::Aç

Fazla Yüklendi. `Open`varsayılan `CFile` oluşturucu ile kullanılmak üzere tasarlanmıştır.

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
İstenilen dosyaya giden yolu içeren dize. Yol göreceli, mutlak veya ağ adı (UNC) olabilir.

*nOpen Bayraklar*<br/>
Dosyanın paylaşım ve erişim modunu tanımlayan bir UINT. Dosyayı açarken yapılacak eylemi belirtir. Bitwise-OR **(&#124;** ) operatörlerini kullanarak seçenekleri birleştirebilirsiniz. Bir erişim izni ve bir paylaşım seçeneği gereklidir; `modeCreate` ve `modeNoInherit` modları isteğe bağlıdır. Mod seçenekleri listesi için [CFile](#cfile) oluşturucuya bakın.

*pHata*<br/>
Başarısız bir işlem durumunu alacak varolan bir dosya özel durum nesnesi için bir işaretçi.

*pTM*<br/>
CAtlTransactionManager nesnesine işaretçi

### <a name="return-value"></a>Dönüş Değeri

Açık başarılı olsaydı sıfırolmayan; aksi takdirde 0. *pError* parametresi yalnızca 0 döndürülürse anlamlıdır.

### <a name="remarks"></a>Açıklamalar

Bu `Open` iki işlev, hatanın normal, beklenen bir durum olduğu bir dosyayı açmak için "güvenli" yöntemlerdir.

`CFile` Oluşturucu bir hata koşulunda bir özel `Open` durum atarken, hata koşulları için FALSE döndürür. `Open`ancak, hatayı açıklamak için bir [CFileException](../../mfc/reference/cfileexception-class.md) nesnesi hala başharflerini açabilir. pError parametresini *pError* sağlamazsanız veya *pError*için NULL'u `Open` geçerseniz, FALSE döndürür ve bir `CFileException`. Varolan `CFileException`bir işaretçiye geçer `Open` ve bir hatayla karşılaşırsanız, işlev bu hatayı açıklayan bilgilerle doldurur. `Open`her iki durumda da bir istisna atmaz.

Aşağıdaki tabloda . `Open`

|`pError`|Karşılaşılan hata|Döndürülen değer|CFileException içeriği|
|--------------|------------------------|------------------|----------------------------|
|NULL|Hayır|TRUE|yok|
|için ptr`CFileException`|Hayır|TRUE|Değişme -den|
|NULL|Evet|FALSE|yok|
|için ptr`CFileException`|Evet|FALSE|hatayı açıklamak için başlatınız|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]

[!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]

## <a name="cfileoperator-handle"></a><a name="operator_handle"></a>CFile::operatör HANDLE

ReadFileEx ve `CFile` [GetFileTime](/windows/win32/api/fileapi/nf-fileapi-readfileex) gibi bir nesneye bir [GetFileTime](/windows/win32/api/fileapi/nf-fileapi-getfiletime) tutamacı geçmek `HANDLE`için bu işleci kullanın.

```
operator HANDLE() const;
```

## <a name="cfileread"></a><a name="read"></a>CFile::Oku

`CFile` Verileri nesneyle ilişkili dosyadan arabelleğe okur.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Dosyadan okunan verileri almak için kullanıcı tarafından sağlanan arabellek için işaretçi.

*nSayısı*<br/>
Dosyadan okunacak maksimum bayt sayısı. Metin modu dosyaları için, satır satır besleme çiftleri tek karakter olarak sayılır.

### <a name="return-value"></a>Dönüş Değeri

Arabelleğe aktarılan bayt sayısı. Tüm `CFile` sınıflar için, dosya nın sonuna ulaşıldıysa, iade değeri *nCount'den* küçük olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]

Başka bir örnek için, [Bkz. CFile::Aç.](#open)

## <a name="cfileremove"></a><a name="remove"></a>CFile::Kaldır

Bu statik işlev, yol tarafından belirtilen dosyayı siler.

```
static void PASCAL Remove(
    LPCTSTR lpszFileName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
İstenilen dosyaya giden yol olan dize. Yol göreceli veya mutlak olabilir ve bir ağ adı içerebilir.

*pTM*<br/>
CAtlTransactionManager nesnesine işaretçi

### <a name="remarks"></a>Açıklamalar

`Remove`dizini kaldırmaz.

Bağlı `Remove` dosya açıksa veya dosya kaldırılamazsa üye işlev bir özel durum oluşturur. Bu işlev DEL komutuna eşdeğerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]

## <a name="cfilerename"></a><a name="rename"></a>CFile::Yeniden Adlandır

Bu statik işlev belirtilen dosyayı yeniden adlandırır.

```
static void PASCAL Rename(
    LPCTSTR lpszOldName,
    LPCTSTR lpszNewName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszOldName*<br/>
Eski yol.

*lpszNewName*<br/>
Yeni yol.

*pTM*<br/>
CAtlTransactionManager nesnesine işaretçi

### <a name="remarks"></a>Açıklamalar

Dizinlerin adı değiştirilenemez. Bu işlev REN komutuna eşdeğerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]

## <a name="cfileseek"></a><a name="seek"></a>CFile::Seek

Dosya işaretçisini açık bir dosyada yeniden konumlandırın.

```
virtual ULONGLONG Seek(
LONGLONG lOff,
UINT nFrom);
```

### <a name="parameters"></a>Parametreler

*lOff*<br/>
Dosya işaretçisini taşımak için bayt sayısı. Pozitif değerler dosya işaretçisini dosyanın sonuna doğru hareket ettirin; negatif değerler dosya işaretçisini dosyanın başlangıcına doğru hareket ettirin.

*nKaynak*<br/>
Aranacak pozisyon. Olası değerler için Açıklamalar bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa dosya işaretçisinin konumu; aksi takdirde, iade değeri tanımsız ve `CFileException` bir özel durum için işaretçi atılır.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda *nFrom* parametresi için olası değerler listeleilmektedir.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::begin`|Dosyanın başından isteyin.|
|`CFile::current`|Dosya işaretçisinin geçerli konumundan arama.|
|`CFile::end`|Dosyanın sonundan isteyin.|

Bir dosya açıldığında, dosya işaretçisi dosyanın başlangıcı olan 0'da konumlandırılır.

Dosya işaretçisini dosyanın sonuna kadar bir konuma ayarlayabilirsiniz. Bunu yaparsanız, dosyaya yazana kadar dosyanın boyutu artmaz.

Bu yöntemiçin özel durum işleyicisi özel durum işlendikten sonra özel durum nesnesi silmek gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]

## <a name="cfileseektobegin"></a><a name="seektobegin"></a>CFile::SeektoBegin

Dosya işaretçisinin değerini dosyanın başına ayarlar.

```
void SeekToBegin();
```

### <a name="remarks"></a>Açıklamalar

`SeekToBegin()`'ye `Seek( 0L, CFile::begin )`eşdeğerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

## <a name="cfileseektoend"></a><a name="seektoend"></a>CFile::Seektoend

Dosya işaretçisinin değerini dosyanın mantıksal sonuna ayarlar.

```
ULONGLONG SeekToEnd();
```

### <a name="return-value"></a>Dönüş Değeri

Baytlar halindeki dosyanın uzunluğu.

### <a name="remarks"></a>Açıklamalar

`SeekToEnd()`'ye `CFile::Seek( 0L, CFile::end )`eşdeğerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

## <a name="cfilesetfilepath"></a><a name="setfilepath"></a>Dosya::SetFilePath

Dosyanın yolunu belirtmek için bu işlevi arayın. Örneğin, bir [CFile](../../mfc/reference/cfile-class.md) nesnesi oluşturulduğunda bir dosyanın yolu `SetFilePath` kullanılamıyorsa, dosyayı sağlamak için arayın.

```
virtual void SetFilePath(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Parametreler

*lpszNewName*<br/>
Yeni yolu belirten bir dize işaretçi.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> `SetFilePath`dosyayı açmaz veya dosyayı oluşturmaz; nesneyi `CFile` yalnızca bir yol adı ile ilişkilendirer ve bu ad daha sonra kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]

## <a name="cfilesetlength"></a><a name="setlength"></a>CFile::Setlength

Dosyanın uzunluğunu değiştirmek için bu işlevi arayın.

```
virtual void SetLength(ULONGLONG dwNewLen);
```

### <a name="parameters"></a>Parametreler

*dwNewLen*<br/>
Baytlarda dosyanın istenilen uzunluğu. Bu değer, dosyanın geçerli uzunluğundan daha büyük veya daha küçük olabilir. Dosya uygun şekilde uzatılır veya kesilir.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Ile `CMemFile`, Bu işlev `CMemoryException` bir nesne atabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]

## <a name="cfilesetstatus"></a><a name="setstatus"></a>CFile::SetStatus

Bu dosya konumuyla ilişkili dosyanın durumunu ayarlar.

```
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,
    const CFileStatus& status,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
İstenilen dosyaya giden yol olan dize. Yol göreceli veya mutlak olabilir ve bir ağ adı içerebilir.

*Durum*<br/>
Yeni durum bilgilerini içeren arabellek. `CFileStatus` Yapıyı `GetStatus` geçerli değerlerle doldurmak için üye işlevi çağırın, ardından gerektiği gibi değişiklikler yapın. Bir değer 0 ise, ilgili durum öğesi güncelleştirilemiyor. Yapının açıklaması için [GetStatus](#getstatus) üye `CFileStatus` işlevine bakın.

*pTM*<br/>
CAtlTransactionManager nesnesine işaretçi

### <a name="remarks"></a>Açıklamalar

Saati ayarlamak için `m_mtime` *durum*alanını değiştirin.

Yalnızca dosyanın özniteliklerini değiştirmek amacıyla bir arama `SetStatus` yaptığınızda `m_mtime` ve dosya durum yapısının üyesi sıfırdan olduğunda, öznitelikler de etkilenebilir (zaman damgasını değiştirmek öznitelikleri üzerinde yan etkilere sahip olabilir). Yalnızca dosyanın özniteliklerini değiştirmek istiyorsanız, önce `m_mtime` dosya durum yapısının üyesini sıfıra `SetStatus`ayarlayın ve ardından ''yi ' için bir çağrı yapın

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]

## <a name="cfileunlockrange"></a><a name="unlockrange"></a>CFile::UnlockRange

Açık bir dosyada bir dizi baytın kilidini açar.

```
virtual void UnlockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Parametreler

*dwPos*<br/>
Kilidini açmak için bayt aralığının başlangıcının bayt mahsulü.

*dwSay*<br/>
Kilidini açmak için aralıktaki bayt sayısı.

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [LockRange](#lockrange) üye işlevinin açıklamasına bakın.

> [!NOTE]
> Bu `CMemFile`işlev- türemiş sınıf için kullanılamaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

## <a name="cfilewrite"></a><a name="write"></a>CFile::Yaz

`CFile` Arabellekten nesneyle ilişkili dosyaya veri yazar.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Dosyaya yazılacak verileri içeren kullanıcı tarafından sağlanan arabellek için bir işaretçi.

*nSayısı*<br/>
Arabellekten aktarılacak bayt sayısı. Metin modu dosyaları için, satır satır besleme çiftleri tek karakter olarak sayılır.

### <a name="remarks"></a>Açıklamalar

`Write`disk dolu durum da dahil olmak üzere çeşitli koşullara yanıt olarak bir özel durum atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]

Ayrıca CFile için örneklere [bakın::CFile](#cfile) ve [CFile::Aç](#open).

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek ÇEKMECE](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CStdioFile Sınıfı](../../mfc/reference/cstdiofile-class.md)<br/>
[CMemFile Sınıfı](../../mfc/reference/cmemfile-class.md)
