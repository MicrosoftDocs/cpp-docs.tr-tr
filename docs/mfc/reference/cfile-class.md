---
description: 'Daha fazla bilgi edinin: CFile sınıfı'
title: CFile sınıfı
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
ms.openlocfilehash: edccd571edf3594d36679a6c4ed6e52df878a705
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184549"
---
# <a name="cfile-class"></a>CFile sınıfı

Microsoft Foundation Class dosya sınıfları için temel sınıf.

## <a name="syntax"></a>Syntax

```
class CFile : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFile:: CFile](#cfile)|`CFile`Bir yol veya dosya tanıtıcısından bir nesne oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFile:: Abort](#abort)|Tüm uyarıları ve hataları yoksayarak bir dosyayı kapatır.|
|[CFile:: Close](#close)|Bir dosyayı kapatır ve nesneyi siler.|
|[CFile::D yukarı](#duplicate)|Bu dosyayı temel alan yinelenen bir nesne oluşturur.|
|[CFile:: Flush](#flush)|Henüz yazılmak üzere tüm verileri temizler.|
|[CFile:: GetFileName](#getfilename)|Seçilen dosyanın dosya adını alır.|
|[CFile:: GetFilePath](#getfilepath)|Seçilen dosyanın tam dosya yolunu alır.|
|[CFile:: GetFileTitle](#getfiletitle)|Seçili dosyanın başlığını alır.|
|[CFile:: GetLength](#getlength)|Dosyanın uzunluğunu alır.|
|[CFile:: GetPosition](#getposition)|Geçerli dosya işaretçisini alır.|
|[CFile:: GetStatus](#getstatus)|Açık dosyanın durumunu alır veya statik sürümde, belirtilen dosyanın (statik, sanal işlev) durumunu alır.|
|[CFile:: LockRange](#lockrange)|Bir dosyadaki bayt aralığını kilitler.|
|[CFile:: Open](#open)|Bir hata-test seçeneğiyle bir dosyayı güvenle açar.|
|[CFile:: Read](#read)|Geçerli dosya konumundaki bir dosyadaki verileri okur (arabelleğe alınmamış).|
|[CFile:: Remove](#remove)|Belirtilen dosyayı siler (statik işlev).|
|[CFile:: Rename](#rename)|Belirtilen dosyayı (static işlevi) yeniden adlandırır.|
|[CFile:: Seek](#seek)|Geçerli dosya işaretçisini konumlandırır.|
|[CFile:: Seektobegın](#seektobegin)|Geçerli dosya işaretçisini dosyanın başlangıcında konumlandırır.|
|[CFile:: SeekToEnd](#seektoend)|Dosyanın sonundaki geçerli dosya işaretçisini konumlandırır.|
|[CFile:: SetFilePath](#setfilepath)|Seçilen dosyanın tam dosya yolunu ayarlar.|
|[CFile:: SetLength](#setlength)|Dosyanın uzunluğunu değiştirir.|
|[CFile:: SetStatus](#setstatus)|Belirtilen dosyanın durumunu (statik, sanal işlev) ayarlar.|
|[CFile:: UnlockRange](#unlockrange)|Dosyadaki bir bayt aralığının kilidini açar.|
|[CFile:: Write](#write)|Dosyadaki verileri geçerli dosya konumuna yazar (arabelleğe alınmamış).|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CFile:: operator işleci](#operator_handle)|Bir nesne için tanıtıcı `CFile` .|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFile:: hFileNull](#hfilenull)|`CFile`Nesnenin geçerli bir tanıtıcıya sahip olup olmadığını belirler.|
|[CFile:: m_hFile](#m_hfile)|Genellikle işletim sistemi dosya tanıtıcısını içerir.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFile:: m_pTM](#m_ptm)|Nesne işaretçisi `CAtlTransactionManager` .|

## <a name="remarks"></a>Açıklamalar

Bu, doğrudan arabelleğe alınmamış, ikili disk giriş/çıkış hizmetleri sağlar ve türetilmiş sınıflar aracılığıyla metin dosyalarını ve bellek dosyalarını dolaylı olarak destekler. `CFile` , `CArchive` Microsoft Foundation Class nesnelerinin serileştirmesini desteklemek için sınıfıyla birlikte çalışarak.

Bu sınıf ve türetilmiş sınıfları arasındaki hiyerarşik ilişki, programınızın tüm dosya nesnelerinde polimorfik arabirim aracılığıyla çalışmasını sağlar `CFile` . Bir bellek dosyası, örneğin bir disk dosyası gibi davranır.

`CFile`Genel amaçlı disk g/ç için ve türetilmiş sınıflarını kullanın. `ofstream` `iostream` Bir disk dosyasına gönderilen biçimlendirilen metin için veya diğer Microsoft sınıflarını kullanın.

Normalde, bir disk dosyası oluşturma sırasında otomatik olarak açılır `CFile` ve yok etme durumunda kapatılır. Statik üye işlevleri, dosyayı açmadan bir dosyanın durumunu sorgulanamıyor izin verir.

Kullanma hakkında daha fazla bilgi için `CFile` bkz. [MFC 'Deki makale dosyaları](../../mfc/files-in-mfc.md) ve *çalışma zamanı kitaplık başvurusunda* [Dosya işleme](../../c-runtime-library/file-handling.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="cfileabort"></a><a name="abort"></a> CFile:: Abort

Bu nesneyle ilişkili dosyayı kapatır ve dosyayı okuma veya yazma için kullanılamaz hale getirir.

```
virtual void Abort();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi yok etmeden önce dosyayı kapatmadıysanız, yıkıcı sizin için kapatır.

Özel durumları işlerken, `CFile::Abort` `CFile::Close` iki önemli şekilde farklılık gösterir. İlk olarak, `Abort` sorunlar tarafından yoksayıldığından, işlev hatalarda bir özel durum oluşturmaz `Abort` . İkincisi, `Abort` Dosya  açılmadıysa veya daha önce kapatılmışsa onay vermez.

**`new`** Nesneyi yığında ayırmak için kullandıysanız `CFile` , dosyayı kapattıktan sonra silmeniz gerekir. `Abort``m_hFile`olarak ayarlanır `CFile::hFileNull` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]

## <a name="cfilecfile"></a><a name="cfile"></a> CFile:: CFile

Bir nesnesi oluşturur ve başlatır `CFile` .

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
Nesneye iliştirilecek dosyanın tanıtıcısı `CFile` .

*lpszFileName*<br/>
Nesneye iliştirilecek bir dosyanın göreli veya tam yolu `CFile` .

*nOpenFlags*<br/>
Belirtilen dosya için dosya erişim seçeneklerinin bit düzeyinde bileşimi (veya). Olası seçenekler için açıklamalar bölümüne bakın.

*pTM*<br/>
CAtlTransactionManager nesnesine yönelik işaretçi

### <a name="remarks"></a>Açıklamalar

Aşağıdaki beş tabloda *nOpenFlags* parametresi için olası seçenekler listelenmektedir.

Aşağıdaki dosya erişim modu seçeneklerinden yalnızca birini seçin. Varsayılan dosya erişim modu, `CFile::modeRead` salt okunurdur.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::modeRead`|Yalnızca okuma erişimini ister.|
|`CFile::modeWrite`|Yalnızca yazma erişimi istekleri.|
|`CFile::modeReadWrite`|Okuma ve yazma erişimi ister.|

Aşağıdaki karakter modu seçeneklerinden birini belirleyin.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::typeBinary`|İkili modu ayarlar (yalnızca türetilmiş sınıflarda kullanılır).|
|`CFile::typeText`|Metin modunu, satır başı satır akışı çiftleri (yalnızca türetilmiş sınıflarda kullanılır) için özel işlemeyle ayarlar.|
|`CFile::typeUnicode`|Unicode modunu ayarlar (yalnızca türetilmiş sınıflarda kullanılır). Uygulama Unicode yapılandırmasında oluşturulduğunda metin, Unicode biçiminde dosyaya yazılır. Dosyaya hiçbir BOM yazılmadı.|

Aşağıdaki dosya paylaşma modu seçeneklerinden yalnızca birini seçin. Varsayılan dosya paylaşma modu, `CFile::shareExclusive` özel.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::shareDenyNone`|Paylaşım kısıtlaması yok.|
|`CFile::shareDenyRead`|Tüm diğerlerine okuma erişimini engeller.|
|`CFile::shareDenyWrite`|Tüm diğerlerine yazma erişimini reddeder.|
|`CFile::shareExclusive`|Tüm diğerlerine okuma ve yazma erişimini reddeder.|

Aşağıdaki dosya oluşturma modu seçeneklerinin ilkini veya her ikisini birden seçin. Varsayılan oluşturma modu, `CFile::modeNoTruncate` mevcut olan açıktır.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::modeCreate`|Dosya yoksa yeni bir dosya oluşturur. Dosya zaten varsa, üzerine yazılır ve başlangıçta sıfır uzunluğa ayarlanır.|
|`CFile::modeNoTruncate`|Dosya yoksa yeni bir dosya oluşturur; Aksi takdirde, dosya zaten varsa `CFile` nesnesine iliştirilir.|

Açıklandığı şekilde aşağıdaki dosya önbelleği seçeneklerini belirleyin. Varsayılan olarak, sistem, seçenek olarak kullanılamayan bir genel amaçlı önbelleğe alma düzeni kullanır.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::osNoBuffer`|Sistem, dosya için ara önbellek kullanmaz. Bu seçenek, aşağıdaki 2 seçenekleri iptal eder.|
|`CFile::osRandomAccess`|Dosya önbelleği rastgele erişim için iyileştirilmiştir. Hem bu seçeneği hem de sıralı tarama seçeneğini kullanmayın.|
|`CFile::osSequentialScan`|Dosya önbelleği sıralı erişim için iyileştirilmiştir. Hem bu seçeneği hem de rastgele erişim seçeneğini kullanmayın.|
|`CFile::osWriteThrough`|Yazma işlemleri gecikme olmadan yapılır.|

Dosya tutamacının devralınmasını engellemek için aşağıdaki güvenlik seçeneğini belirleyin. Varsayılan olarak, tüm yeni alt süreçler dosya tanıtıcısını kullanabilir.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::modeNoInherit`|Tüm alt işlemlerin dosya tanıtıcısını kullanmasını önler.|

Varsayılan Oluşturucu, üyeleri başlatır ancak nesneye bir dosya ekler `CFile` . Bu oluşturucuyu kullandıktan sonra, bir dosyayı açmak ve nesneye iliştirmek için [CFile:: Open](#open) metodunu kullanın `CFile` .

Tek parametreli Oluşturucu üyeleri başlatır ve var olan bir dosyayı `CFile` nesnesine ekler.

İki parametreli Oluşturucu üyeleri başlatır ve belirtilen dosyayı açmaya çalışır. Bu Oluşturucu belirtilen dosyayı başarıyla açarsa, dosya `CFile` nesneye iliştirilir; Aksi takdirde, bu Oluşturucu bir nesne işaretçisi oluşturur `CInvalidArgException` . Özel durumların nasıl işleneceği hakkında daha fazla bilgi için bkz. [özel durumlar](../../mfc/exception-handling-in-mfc.md).

Bir `CFile` nesne belirtilen dosyayı başarıyla açarsa, nesne yok edildiğinde bu dosyayı otomatik olarak kapatır `CFile` ; Aksi takdirde, artık nesneye iliştirildikten sonra dosyayı açık bir şekilde kapatmanız gerekir `CFile` .

### <a name="example"></a>Örnek

Aşağıdaki kod, ' nin nasıl kullanılacağını göstermektedir `CFile` .

[!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]

## <a name="cfileclose"></a><a name="close"></a> CFile:: Close

Bu nesneyle ilişkili dosyayı kapatır ve dosyayı okuma veya yazma için kullanılamaz hale getirir.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi yok etmeden önce dosyayı kapatmadıysanız, yıkıcı sizin için kapatır.

**`new`** Nesneyi yığında ayırmak için kullandıysanız `CFile` , dosyayı kapattıktan sonra silmeniz gerekir. `Close``m_hFile`olarak ayarlanır `CFile::hFileNull` .

### <a name="example"></a>Örnek

[CFile:: CFile](#cfile)örneğine bakın.

## <a name="cfileduplicate"></a><a name="duplicate"></a> CFile::D yukarı

`CFile`Belirli bir dosya için yinelenen bir nesne oluşturur.

```
virtual CFile* Duplicate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yinelenen nesneye yönelik bir işaretçi `CFile` .

### <a name="remarks"></a>Açıklamalar

Bu işlev, C çalışma zamanı işlevine eşdeğerdir `_dup` .

## <a name="cfileflush"></a><a name="flush"></a> CFile:: Flush

Dosya arabelleğinde kalan tüm verileri dosyaya yazılmasına zorlar.

```
virtual void Flush();
```

### <a name="remarks"></a>Açıklamalar

Kullanımı, `Flush` arabelleklerin temizlenme garantisi vermez `CArchive` . Bir arşiv kullanıyorsanız, önce [CArchive:: Flush](../../mfc/reference/carchive-class.md#flush) çağırın.

### <a name="example"></a>Örnek

[CFile:: SetFilePath](#setfilepath)örneğine bakın.

## <a name="cfilegetfilename"></a><a name="getfilename"></a> CFile:: GetFileName

Belirtilen bir dosyanın adını almak için bu üye işlevini çağırın.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosyanın adı.

### <a name="remarks"></a>Açıklamalar

Örneğin, `GetFileName` dosyaya dosya hakkında bir ileti oluşturmak için çağırdığınızda dosya `c:\windows\write\myfile.wri` adı `myfile.wri` döndürülür.

Adı da dahil olmak üzere dosyanın tüm yolunu döndürmek için [GetFilePath](#getfilepath)' i çağırın. Dosyanın () başlığını döndürmek için `myfile` [GetFileTitle](#getfiletitle)çağırın.

### <a name="example"></a>Örnek

Bu kod parçası, WINDOWS dizininizde SYSTEM.INI dosyasını açar. Bulunursa örnek, çıkış bölümünde gösterildiği gibi adı ve yolu ve başlığı yazdırır:

[!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]

## <a name="cfilegetfilepath"></a><a name="getfilepath"></a> CFile:: GetFilePath

Belirtilen bir dosyanın tam yolunu almak için bu üye işlevi çağırın.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dosyanın tam yolu.

### <a name="remarks"></a>Açıklamalar

Örneğin, `GetFilePath` kullanıcıya dosya hakkında bir ileti oluşturmak için öğesini çağırdığınızda `c:\windows\write\myfile.wri` dosya yolu `c:\windows\write\myfile.wri` döndürülür.

Yalnızca dosyanın adını () döndürmek için `myfile.wri` [GetFileName](#getfilename)' i çağırın. Dosyanın () başlığını döndürmek için `myfile` [GetFileTitle](#getfiletitle)çağırın.

### <a name="example"></a>Örnek

[GetFileName](#getfilename)örneğine bakın.

## <a name="cfilegetfiletitle"></a><a name="getfiletitle"></a> CFile:: GetFileTitle

Dosya için dosya başlığını (görünen ad) almak için bu üye işlevi çağırın.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan dosyanın başlığı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, dosyanın başlığını almak için [GetFileTitle](/windows/win32/api/commdlg/nf-commdlg-getfiletitlew) öğesini çağırır. Başarılı olursa, yöntemi, sistemin Kullanıcı için dosya adını göstermek için kullanacağı dizeyi döndürür. Aksi takdirde, yöntemi, temel alınan dosyanın dosya adını (dosya uzantısı dahil) almak için [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) öğesini çağırır. Bu, dosya uzantısının döndürülen dosya başlığı dizesine her zaman dahil olmadığı anlamına gelir. Daha fazla bilgi için Windows SDK [GetFileTitle](/windows/win32/api/commdlg/nf-commdlg-getfiletitlew) ve [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew) bölümüne bakın.

Adı da dahil olmak üzere dosyanın tüm yolunu döndürmek için [GetFilePath](#getfilepath)' i çağırın. Yalnızca dosyanın adını döndürmek için [GetFileName](#getfilename)' i çağırın.

### <a name="example"></a>Örnek

[GetFileName](#getfilename)örneğine bakın.

## <a name="cfilegetlength"></a><a name="getlength"></a> CFile:: GetLength

Dosyanın geçerli mantıksal uzunluğunu bayt cinsinden edinir.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosyanın uzunluğu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]

## <a name="cfilegetposition"></a><a name="getposition"></a> CFile:: GetPosition

Daha sonraki çağrılarında kullanılabilen dosya işaretçisinin geçerli değerini alır `Seek` .

```
virtual ULONGLONG GetPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]

## <a name="cfilegetstatus"></a><a name="getstatus"></a> CFile:: GetStatus

Bu yöntem, belirli bir nesne örneğiyle ilgili durum bilgilerini `CFile` veya belirli bir dosya yolunu alır.

```
BOOL GetStatus(CFileStatus& rStatus) const;

static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*rStatus*<br/>
`CFileStatus`Durum bilgilerini alacak Kullanıcı tarafından sağlanan yapıya başvuru. `CFileStatus`Yapı aşağıdaki alanlara sahiptir:

- `CTime m_ctime` Dosyanın oluşturulduğu tarih ve saat.

- `CTime m_mtime` Dosyanın son değiştirildiği tarih ve saat.

- `CTime m_atime` Dosyanın okuma için son erişildiği tarih ve saat.

- `ULONGLONG m_size` DIZIN komutu tarafından raporlanarak dosyanın bayt cinsinden mantıksal boyutu.

- `BYTE m_attribute` Dosyanın öznitelik baytı.

- `char m_szFullName[_MAX_PATH]` Windows karakter kümesindeki mutlak dosya adı.

*lpszFileName*<br/>
Windows karakter kümesindeki, istenen dosyanın yolu olan bir dize. Yol göreli veya mutlak olabilir ya da bir ağ yolu adı içerebilir.

*pTM*<br/>
CAtlTransactionManager nesnesine yönelik işaretçi

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dosya için durum bilgisi başarıyla elde edilmişse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Statik olmayan sürümü, `GetStatus` belirtilen nesneyle ilişkili açık dosyanın durum bilgilerini alır `CFile` .  Statik sürümü, dosyayı `GetStatus` gerçekten açmadan belirli bir dosya yolundan dosya durumunu alır. Bu sürüm, bir dosyanın mevcut ve erişim haklarının test edilmesi için yararlıdır.

`m_attribute` `CFileStatus` Yapının üyesi dosya özniteliği kümesine başvurur. `CFile`Sınıf, dosya özniteliklerinin simgelenebilir olarak belirtime Için **öznitelik** numaralandırma türünü sağlar:

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

## <a name="cfilehfilenull"></a><a name="hfilenull"></a> CFile:: hFileNull

Nesne için geçerli bir dosya tanıtıcısının varlığını belirler `CFile` .

```
static AFX_DATA const HANDLE hFileNull;
```

### <a name="remarks"></a>Açıklamalar

Bu sabit, `CFile` nesnenin geçerli bir dosya tutamacı olup olmadığını tespit etmek için kullanılır.

Aşağıdaki örnekte bu işlem gösterilmektedir:

[!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]

## <a name="cfilelockrange"></a><a name="lockrange"></a> CFile:: LockRange

Dosya zaten kilitliyse bir özel durum oluşturan bir açık dosyadaki bayt aralığını kilitler.

```
virtual void LockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Parametreler

*dwPos*<br/>
Kilitleme için bayt aralığının başlangıcının bayt kayması.

*dwCount*<br/>
Kilitlenecek aralıktaki bayt sayısı.

### <a name="remarks"></a>Açıklamalar

Bir dosyadaki kilitleme baytları diğer işlemlere göre bu baytlara erişimi engeller. Bir dosyanın birden fazla bölgesini kilitleyebilmeniz, ancak çakışan bölgelere izin verilmez.

Üye işlevini kullanarak bölgenin kilidini açtığınızda `UnlockRange` , bayt aralığı, daha önce kilitlenen bölgeye tam olarak karşılık gelmelidir. `LockRange`İşlev bitişik bölgeleri birleştirmiyor. İki kilitli bölge bitişik ise, her bir bölgenin kilidini ayrı olarak açmanız gerekir.

> [!NOTE]
> Bu işlev, `CMemFile` türetilmiş sınıf için kullanılamaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

## <a name="cfilem_hfile"></a><a name="m_hfile"></a> CFile:: m_hFile

Açık bir dosya için işletim sistemi dosya tanıtıcısını içerir.

```
HANDLE m_hFile;
```

### <a name="remarks"></a>Açıklamalar

`m_hFile` , UINT türünde genel bir değişkendir. `CFile::hFileNull`Tanıtıcı atanmamışsa, işletim sisteminin bağımsız boş bir dosya göstergesi içerir.

`m_hFile`Üyenin anlamı türetilmiş sınıfa bağlı olduğundan, kullanılması önerilmez. `m_hFile` , sınıfının polimorfik olmayan kullanımını destekleme konusunda kolaylık sağlaması için genel bir üye yapılır.

## <a name="cfilem_ptm"></a><a name="m_ptm"></a> CFile:: m_pTM

Bir nesne işaretçisi `CAtlTransactionManager` .

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

## <a name="cfileopen"></a><a name="open"></a> CFile:: Open

Fazla Yüklendi. `Open` Varsayılan Oluşturucu ile kullanılmak üzere tasarlanmıştır `CFile` .

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
İstenen dosyanın yolunu içeren bir dize. Yol göreli, mutlak veya ağ adı (UNC) olabilir.

*nOpenFlags*<br/>
Dosyanın paylaşım ve erişim modunu tanımlayan bir UINT. Dosya açılırken gerçekleştirilecek eylemi belirtir. Bit düzeyinde OR ( **&#124;** ) işlecini kullanarak seçenekleri birleştirebilirsiniz. Bir erişim izni ve bir paylaşma seçeneği gereklidir; `modeCreate` ve `modeNoInherit` modları isteğe bağlıdır. Mod seçeneklerinin bir listesi için bkz. [CFile](#cfile) Oluşturucusu.

*pError*<br/>
Hatalı bir işlemin durumunu alacak olan, var olan bir dosya özel durum nesnesine yönelik bir işaretçi.

*pTM*<br/>
CAtlTransactionManager nesnesine yönelik işaretçi

### <a name="return-value"></a>Dönüş Değeri

Açma başarılı olursa sıfır dışı; Aksi takdirde 0. *PError* parametresi yalnızca 0 döndürülürse anlamlı olur.

### <a name="remarks"></a>Açıklamalar

İki `Open` işlev, bir hatanın normal, beklenen bir koşul olduğu bir dosyayı açmaya yönelik "güvenli" yöntemlerdir.

`CFile`Oluşturucu bir hata koşulunda özel durum oluşturduğunda, `Open` hata koşulları için false döndürür. `Open` , hatayı anlatmak için yine de bir [CFileException](../../mfc/reference/cfileexception-class.md) nesnesi başlatabilir. *PError* parametresini sağlamadıysanız veya *PERROR* için null değeri geçirirseniz, `Open` false değerini döndürür ve oluşturmaz `CFileException` . Var olan bir işaretçi varsa `CFileException` ve bir `Open` hatayla karşılaşırsa, işlev bu hatayı açıklayan bilgilerle doldurulur. `Open` Her iki durumda da bir özel durum oluşturmaz.

Aşağıdaki tabloda, olası sonuçları açıklanmaktadır `Open` .

| `pError` | Hatayla karşılaşıldı | Döndürülen değer | CFileException içeriği |
|--|--|--|--|
| NULL | Hayır | TRUE | yok |
| için PTR `CFileException` | Hayır | TRUE | değiştirilmediği |
| NULL | Evet | FALSE | yok |
| için PTR `CFileException` | Evet | FALSE | hatayı tanımlayacak şekilde başlatıldı |

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]

[!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]

## <a name="cfileoperator-handle"></a><a name="operator_handle"></a> CFile:: operator işleci

`CFile` [ReadFileEx](/windows/win32/api/fileapi/nf-fileapi-readfileex) ve [GetFileTime](/windows/win32/api/fileapi/nf-fileapi-getfiletime) gibi işlevlere bir nesneye bir tanıtıcı geçirmek için bu işleci kullanın `HANDLE` .

```
operator HANDLE() const;
```

## <a name="cfileread"></a><a name="read"></a> CFile:: Read

Nesneyle ilişkili dosyadaki verileri arabelleğe okur `CFile` .

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parametreler

*Lparabelleğe*<br/>
Dosyadan okunan verileri alacak Kullanıcı tarafından sağlanan arabelleğin işaretçisi.

*nCount*<br/>
Dosyadan okunacak en fazla bayt sayısı. Metin modu dosyaları için satır başı satır besleme çiftleri tek karakter olarak sayılır.

### <a name="return-value"></a>Dönüş Değeri

Arabelleğe aktarılan baytların sayısı. Tüm `CFile` sınıflar için, dosya sonuna ulaşılırsa dönüş değeri *nCount* 'tan daha az olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]

Diğer bir örnek için bkz. [CFile:: Open](#open).

## <a name="cfileremove"></a><a name="remove"></a> CFile:: Remove

Bu statik işlev, yol tarafından belirtilen dosyayı siler.

```
static void PASCAL Remove(
    LPCTSTR lpszFileName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
İstenen dosyanın yolu olan bir dize. Yol göreli veya mutlak olabilir ve bir ağ adı içerebilir.

*pTM*<br/>
CAtlTransactionManager nesnesine yönelik işaretçi

### <a name="remarks"></a>Açıklamalar

`Remove` bir dizin kaldırılmaz.

`Remove`Üye işlevi, bağlı dosya açıksa veya dosya kaldırılamadığı takdirde bir özel durum oluşturur. Bu işlev DEL komutuna eşdeğerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]

## <a name="cfilerename"></a><a name="rename"></a> CFile:: Rename

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
CAtlTransactionManager nesnesine yönelik işaretçi

### <a name="remarks"></a>Açıklamalar

Dizinler yeniden adlandırılamaz. Bu işlev, REN komutuna eşdeğerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]

## <a name="cfileseek"></a><a name="seek"></a> CFile:: Seek

Dosya işaretçisini açık bir dosyada konumlandırır.

```
virtual ULONGLONG Seek(
LONGLONG lOff,
UINT nFrom);
```

### <a name="parameters"></a>Parametreler

*lOff*<br/>
Dosya işaretçisini taşıyacağınız bayt sayısı. Pozitif değerler dosya işaretçisini dosyanın sonuna doğru taşır; negatif değerler dosya işaretçisini dosyanın başlangıcına doğru taşır.

*Ngüncelleştirmelerini*<br/>
Arama yapılacak konum. Olası değerler için açıklamalar bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa dosya işaretçisinin konumu; Aksi takdirde, dönüş değeri tanımsızdır ve bir `CFileException` özel durum işaretçisi oluşturulur.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda, *nFrom* parametresi için olası değerler listelenmektedir.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::begin`|Dosyanın başından itibaren arama yapın.|
|`CFile::current`|Dosya işaretçisinin geçerli konumundan arama yapın.|
|`CFile::end`|Dosyanın sonundan ara.|

Dosya açıldığında dosya işaretçisi, dosyanın başlangıcında 0 ' a yerleştirilir.

Dosya işaretçisini dosya sonunun ötesinde bir konuma ayarlayabilirsiniz. Bunu yaparsanız, dosyanın boyutu dosyaya yazana kadar artmaz.

Bu yöntem için özel durum işleyicisi, özel durum işlendikten sonra özel durum nesnesini silmesi gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]

## <a name="cfileseektobegin"></a><a name="seektobegin"></a> CFile:: Seektobegın

Dosya işaretçisinin değerini dosyanın başlangıcına ayarlar.

```cpp
void SeekToBegin();
```

### <a name="remarks"></a>Açıklamalar

`SeekToBegin()`, `Seek( 0L, CFile::begin )` ile eşdeğerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

## <a name="cfileseektoend"></a><a name="seektoend"></a> CFile:: SeekToEnd

Dosya işaretçisinin değerini dosyanın mantıksal sonuna ayarlar.

```
ULONGLONG SeekToEnd();
```

### <a name="return-value"></a>Dönüş Değeri

Dosyanın bayt cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

`SeekToEnd()`, `CFile::Seek( 0L, CFile::end )` ile eşdeğerdir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

## <a name="cfilesetfilepath"></a><a name="setfilepath"></a> CFile:: SetFilePath

Dosyanın yolunu belirtmek için bu işlevi çağırın. Örneğin, bir [CFile](../../mfc/reference/cfile-class.md) nesnesi oluşturulduğunda bir dosyanın yolu kullanılabilir değilse, `SetFilePath` bunu sağlamak için çağırın.

```
virtual void SetFilePath(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Parametreler

*lpszNewName*<br/>
Yeni yolu belirten bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> `SetFilePath` dosyayı açmaz veya dosyayı oluşturmaz; `CFile` nesneyi, daha sonra kullanılabilecek bir yol adıyla ilişkilendirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]

## <a name="cfilesetlength"></a><a name="setlength"></a> CFile:: SetLength

Dosyanın uzunluğunu değiştirmek için bu işlevi çağırın.

```
virtual void SetLength(ULONGLONG dwNewLen);
```

### <a name="parameters"></a>Parametreler

*dwNewLen*<br/>
Dosyanın bayt cinsinden istenen uzunluğu. Bu değer, dosyanın geçerli uzunluğundan daha büyük veya daha küçük olabilir. Dosya uygun şekilde genişletilir veya kesilmeyecektir.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> İle `CMemFile` , bu işlev bir nesne oluşturabilir `CMemoryException` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]

## <a name="cfilesetstatus"></a><a name="setstatus"></a> CFile:: SetStatus

Bu dosya konumuyla ilişkili dosyanın durumunu ayarlar.

```
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,
    const CFileStatus& status,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
İstenen dosyanın yolu olan bir dize. Yol göreli veya mutlak olabilir ve bir ağ adı içerebilir.

*durumlarına*<br/>
Yeni durum bilgilerini içeren arabellek. `GetStatus`Yapıyı geçerli değerlerle önceden doldurmanız için üye işlevini çağırın `CFileStatus` , sonra da gerekli değişiklikleri yapın. Değer 0 ise, ilgili durum öğesi güncellenmez. Yapının açıklaması için [GetStatus](#getstatus) üye işlevine bakın `CFileStatus` .

*pTM*<br/>
CAtlTransactionManager nesnesine yönelik işaretçi

### <a name="remarks"></a>Açıklamalar

Saati ayarlamak için, `m_mtime` *durum* alanını değiştirin.

`SetStatus`Yalnızca dosyanın özniteliklerini değiştirme girişiminde bir çağrı yaptığınızda ve `m_mtime` dosya durumu yapısının üyesi sıfır değilse, öznitelikler de etkilenebilir (zaman damgasının değiştirilmesi özniteliklerde yan etkilere sahip olabilir). Yalnızca dosyanın özniteliklerini değiştirmek istiyorsanız, önce `m_mtime` dosya durumu yapısının üyesini sıfır olarak ayarlayın ve sonra bir çağrısı yapın `SetStatus` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]

## <a name="cfileunlockrange"></a><a name="unlockrange"></a> CFile:: UnlockRange

Açık bir dosyadaki bir bayt aralığının kilidini açar.

```
virtual void UnlockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Parametreler

*dwPos*<br/>
Kilit açma için bayt aralığının başlangıcının bayt kayması.

*dwCount*<br/>
Kilit açılacak aralıktaki bayt sayısı.

### <a name="remarks"></a>Açıklamalar

Ayrıntılar için [LockRange](#lockrange) üye işlevinin açıklamasına bakın.

> [!NOTE]
> Bu işlev, türetilmiş sınıf için kullanılamaz `CMemFile` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

## <a name="cfilewrite"></a><a name="write"></a> CFile:: Write

Bir arabellekteki verileri nesneyle ilişkili dosyaya yazar `CFile` .

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parametreler

*Lparabelleğe*<br/>
Dosyaya yazılacak verileri içeren Kullanıcı tarafından sağlanan arabelleğe yönelik bir işaretçi.

*nCount*<br/>
Arabellekten aktarılacak bayt sayısı. Metin modu dosyaları için satır başı satır besleme çiftleri tek karakter olarak sayılır.

### <a name="remarks"></a>Açıklamalar

`Write` disk tam koşulu da dahil olmak üzere çeşitli koşullara yanıt olarak bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]

Ayrıca [CFile:: CFile](#cfile) ve [CFile:: Open](#open)örneklerine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek DRAWCLı](../../overview/visual-cpp-samples.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CStdioFile sınıfı](../../mfc/reference/cstdiofile-class.md)<br/>
[CMemFile sınıfı](../../mfc/reference/cmemfile-class.md)
