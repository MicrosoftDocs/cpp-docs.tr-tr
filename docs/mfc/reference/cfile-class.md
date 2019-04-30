---
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
ms.openlocfilehash: db499ffa5f1d82b6e3622287f86132930a929102
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385316"
---
# <a name="cfile-class"></a>CFile sınıfı

Microsoft Foundation Class dosya sınıfları için temel sınıf.

## <a name="syntax"></a>Sözdizimi

```
class CFile : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFile::CFile](#cfile)|Oluşturur bir `CFile` nesne yolu veya dosya tanıtıcısı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFile::Abort](#abort)|Tüm uyarıları ve hataları yoksayma dosyayı kapatır.|
|[CFile::Close](#close)|Bir dosyayı kapatır ve nesneyi siler.|
|[CFile::Duplicate](#duplicate)|Bu dosyasını temel alan yinelenen bir nesne oluşturur.|
|[CFile::Flush](#flush)|Henüz yazılacak tüm verileri temizler.|
|[CFile::GetFileName](#getfilename)|Seçili dosya adını alır.|
|[CFile::GetFilePath](#getfilepath)|Seçilen dosyanın tam yolunu alır.|
|[CFile::GetFileTitle](#getfiletitle)|Seçili dosya başlığını alır.|
|[CFile::GetLength](#getlength)|Dosya uzunluğunu alır.|
|[CFile::GetPosition](#getposition)|Geçerli dosya işaretçisini alır.|
|[CFile::GetStatus](#getstatus)|Açık dosyanın ya da statik sürümünde alır, belirtilen dosya (statik, sanal işlev) durumunu alır.|
|[CFile::LockRange](#lockrange)|Bir dosyadaki bir bayt aralığı kilitler.|
|[CFile::Open](#open)|Güvenli bir şekilde hata test etme seçeneği ile bir dosya açar.|
|[CFile::Read](#read)|Geçerli dosya konumu, bir dosyaya (arabellekten çıkarılan) verileri okur.|
|[CFile::Remove](#remove)|Belirtilen dosya (statik işlev) siler.|
|[CFile::Rename](#rename)|(Statik işlev) belirtilen dosyayı yeniden adlandırır.|
|[CFile::Seek](#seek)|Geçerli dosya işaretçisini yerleştirir.|
|[CFile::SeekToBegin](#seektobegin)|Geçerli dosya işaretçisini dosyanın başında yerleştirir.|
|[CFile::SeekToEnd](#seektoend)|Geçerli dosya işaretçisini dosyanın sonuna konumlandırır.|
|[CFile::SetFilePath](#setfilepath)|Seçilen dosyanın tam yolunu ayarlar.|
|[CFile::SetLength](#setlength)|Dosya uzunluğu değiştirir.|
|[CFile::SetStatus](#setstatus)|Belirtilen dosya (statik, sanal işlev) durumunu ayarlar.|
|[CFile::UnlockRange](#unlockrange)|Bir dosyadaki bir bayt aralığı kilidini açar.|
|[CFile::Write](#write)|(Arabellekten çıkarılan) veri geçerli dosya konumu bir dosyaya yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CFile::operator TANITICISI](#operator_handle)|İçin bir tanıtıcı bir `CFile` nesne.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFile::hFileNull](#hfilenull)|Belirler `CFile` nesnesi geçerli bir tanıtıcı sahiptir.|
|[CFile::m_hFile](#m_hfile)|Genellikle işletim sistemi dosya tanıtıcısı içerir.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFile::m_pTM](#m_ptm)|İşaretçi `CAtlTransactionManager` nesne.|

## <a name="remarks"></a>Açıklamalar

Doğrudan ara bellekten çıkarılan, ikili disk giriş/çıkış hizmetlerini sağlar ve metin dosyaları ve bellek dosyaları ondan türetilen sınıflardan aracılığıyla dolaylı olarak destekler. `CFile` ile birlikte çalışır `CArchive` Microsoft Foundation Class nesneleri serileştirmek desteklemek için sınıf.

Bu sınıf ve türetilmiş sınıflarının arasındaki hiyerarşik ilişkiyi polimorfik aracılığıyla tüm dosya nesneler üzerinde çalışılacak programınızı sağlar `CFile` arabirimi. Bir bellek dosyası, örneğin, bir disk dosyası gibi davranır.

Kullanım `CFile` genel amaçlı disk g/ç için türetilmiş sınıfları. Kullanım `ofstream` veya diğer Microsoft iostream sınıfları disk dosyasına gönderilen biçimlendirilmiş metni.

Normalde, bir disk dosyası otomatik olarak açılan `CFile` oluşturma ve üzerinde kapalı yok etme. Statik üye işlevleri dosyayı açmaya gerek kalmadan bir dosyanın durumunu sorgulayın izin verir.

Kullanma hakkında daha fazla bilgi için `CFile`, makalelere göz atın [MFC'deki dosyalar](../../mfc/files-in-mfc.md) ve [dosya işleme](../../c-runtime-library/file-handling.md) içinde *çalışma zamanı kitaplığı başvurusu*.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CFile`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="abort"></a>  CFile::Abort

Bu nesneyle ilişkili dosyayı kapatır ve dosyanın okuma veya yazma için kullanılabilir hale getirir.

```
virtual void Abort();
```

### <a name="remarks"></a>Açıklamalar

Dosya nesne yok etme öncesinde kapatılmamış, yok edici sizin için kapatılır.

Özel durumlar, işlerken `CFile::Abort` farklıdır `CFile::Close` iki önemli şekilde. İlk olarak, `Abort` işlevi değil oluşturur bir özel durum hatalarında hataları tarafından göz ardı edilir çünkü `Abort`. İkinci olarak, `Abort` yapmamayı **ASSERT** dosya açılmamış olan ya da daha önce kapatıldı.

Kullandıysanız **yeni** ayrılacak `CFile` dosya kapattıktan sonra silmelisiniz yığında nesne. `Abort` Ayarlar `m_hFile` için `CFile::hFileNull`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]

##  <a name="cfile"></a>  CFile::CFile

Oluşturur ve başlatır bir `CFile` nesne.

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

*Hfıle*<br/>
İliştirilecek dosya tanıtıcısı `CFile` nesne.

*lpszFileName*<br/>
Eklemek için bir dosyanın göreli veya tam yolunu `CFile` nesne.

*nOpenFlags*<br/>
Bit düzeyinde birleşimi (veya) belirtilen dosya için dosya erişim seçenekleri. Olası seçenek için Açıklamalar bölümüne bakın.

*pTM*<br/>
CAtlTransactionManager nesne işaretçisi

### <a name="remarks"></a>Açıklamalar

Aşağıdaki beş tablolar için olası seçeneklerin listesi *nOpenFlags* parametresi.

Aşağıdaki dosya erişim modu seçeneklerden yalnızca birini seçin. Varsayılan dosya erişim mod `CFile::modeRead`, hangi salt okunur.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::modeRead`|Yalnızca istekleri okuma erişimi.|
|`CFile::modeWrite`|Yalnızca istekleri yazma erişimi.|
|`CFile::modeReadWrite`|İstekleri okuma ve yazma erişimi.|

Karakter modu şunlardan birini seçin.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::typeBinary`|İkili mod (yalnızca türetilmiş sınıflarda kullanılır) ayarlar.|
|`CFile::typeText`|(Yalnızca türetilmiş sınıflarda kullanılır), satır başı satır besleme çiftleri için özel işleme ile metin modunu ayarlar.|
|`CFile::typeUnicode`|Unicode modu (yalnızca türetilmiş sınıflarda kullanılır) ayarlar. Uygulama bir Unicode yapılandırmasında yapılandırıldığında metin dosyayı Unicode biçiminde yazılır. Hiçbir BOM dosyasına yazılır.|

Dosya Paylaşımı modu şunlardan birini seçin. Varsayılan dosya paylaşımı mod `CFile::shareExclusive`, özel olduğu.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::shareDenyNone`|Paylaşım kısıtlaması yoktur.|
|`CFile::shareDenyRead`|Diğer tüm okuma erişimi engeller.|
|`CFile::shareDenyWrite`|Diğer tüm yazma erişimi engeller.|
|`CFile::shareExclusive`|Okuma ve yazma erişimi için diğer tüm reddeder.|

İlk veya her ikisi de aşağıdaki dosya oluşturma modu seçeneklerden birini seçin. Varsayılan oluşturma modu `CFile::modeNoTruncate`, var olan açık olduğu.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::modeCreate`|Hiçbir dosya varsa, yeni bir dosya oluşturur. Dosya zaten varsa üzerine ve ilk başta sıfır uzunluğa ayarlayın.|
|`CFile::modeNoTruncate`|Hiçbir dosya varsa, yeni bir dosya oluşturur; Dosya zaten varsa, aksi takdirde, bağlı olduğu `CFile` nesne.|

Önbellek seçeneklerini açıklandığı aşağıdaki dosyayı seçin. Varsayılan olarak, bir genel amaçlı bir seçenek olarak kullanılabilir değil düzeni önbelleğe alma sistemi kullanır.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::osNoBuffer`|Sistem, dosya için bir ara önbellek kullanmaz. Bu seçenek, aşağıdaki 2 seçenek iptal eder.|
|`CFile::osRandomAccess`|Dosya önbelleği, rastgele erişim için optimize edilmiştir. Bu seçenek ve sıralı Tarama seçeneğini kullanmayın.|
|`CFile::osSequentialScan`|Dosya önbelleği sıralı erişim için optimize edilmiştir. Bu seçenek ve rastgele erişim seçeneğini kullanmayın.|
|`CFile::osWriteThrough`|Yazma gecikme olmadan işlemler gerçekleştirilir.|

Dosya tanıtıcısı devralınmasını önlemek için aşağıdaki güvenlik seçeneği belirleyin. Varsayılan olarak, tüm yeni alt işlemleri dosya tanıtıcısı kullanabilirsiniz.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::modeNoInherit`|Herhangi bir alt işlem, dosya tanıtıcısını kullanmasını önler.|

Varsayılan Oluşturucu üye başlatır, ancak bir dosyaya eklemez `CFile` nesne. Bu oluşturucu kullandıktan sonra kullanmak [CFile::Open](#open) bir dosyasını açın ve ekler için yöntem `CFile` nesne.

Bir parametreli Oluşturucusu üyeleri başlatır ve varolan bir dosyaya ekler `CFile` nesne.

İki parametre oluşturucuyla üyeleri başlatır ve belirtilen dosyayı açmaya çalışır. Bu oluşturucu belirtilen dosya başarıyla açılır, dosyanın bağlı `CFile` nesne; Aksi takdirde, bu oluşturucu işaretçisi oluşturur bir `CInvalidArgException` nesne. Özel durumları işleme hakkında daha fazla bilgi için bkz. [özel durumları](../../mfc/exception-handling-in-mfc.md).

Varsa bir `CFile` nesne başarıyla belirtilen bir dosya açıldığında, bunu bu dosya otomatik olarak ne zaman kapanacak `CFile` nesnesi yok edildiğinde; Aksi takdirde, artık ekli olduğu sonra dosyayı açıkça kapatmalısınız `CFile` nesne.

### <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanılacağını gösterir. bir `CFile`.

[!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]

##  <a name="close"></a>  CFile::Close

Bu nesneyle ilişkili dosyayı kapatır ve dosyanın okuma veya yazma için kullanılabilir hale getirir.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Dosya nesne yok etme öncesinde kapatılmamış, yok edici sizin için kapatılır.

Kullandıysanız **yeni** ayrılacak `CFile` dosya kapattıktan sonra silmelisiniz yığında nesne. `Close` Ayarlar `m_hFile` için `CFile::hFileNull`.

### <a name="example"></a>Örnek

Örneğin bakın [CFile::CFile](#cfile).

##  <a name="duplicate"></a>  CFile::Duplicate

Yinelenen yapıları `CFile` nesne için belirli bir dosya.

```
virtual CFile* Duplicate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yinelenen bir işaretçiye `CFile` nesne.

### <a name="remarks"></a>Açıklamalar

Bu C çalışma zamanı işlevine eşdeğerdir `_dup`.

##  <a name="flush"></a>  CFile::Flush

Dosyaya yazılacak dosya arabelleğinde kalan herhangi bir veri zorlar.

```
virtual void Flush();
```

### <a name="remarks"></a>Açıklamalar

Kullanımını `Flush` , temizleme garanti etmez `CArchive` arabellek. Bir arşiv kullanıyorsanız, çağrı [CArchive::Flush](../../mfc/reference/carchive-class.md#flush) ilk.

### <a name="example"></a>Örnek

Örneğin bakın [CFile::SetFilePath](#setfilepath).

##  <a name="getfilename"></a>  CFile::GetFileName

Belirtilen dosya adını almak için bu üye işlevini çağırın.

```
virtual CString GetFileName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosyanın adı.

### <a name="remarks"></a>Açıklamalar

Örneğin, çağırdığınızda `GetFileName` kullanıcıya dosyası hakkında bir ileti oluşturmak için `c:\windows\write\myfile.wri`, dosya `myfile.wri`, döndürülür.

Dosyanın adı dahil olmak üzere yolun tamamını döndürülecek çağrı [GetFilePath](#getfilepath). Dosyanın başlığı döndürülecek ( `myfile`), çağrı [GetFileTitle](#getfiletitle).

### <a name="example"></a>Örnek

Bu kod parçası sistem açar. WINDOWS dizinindeki INI dosyası. Bulundu, örnek adı ve yolu ve başlık, çıkış altında gösterildiği yazdıran System.Diagnostics.defaulttracelistener'ı varsa:

[!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]

##  <a name="getfilepath"></a>  CFile::GetFilePath

Belirli bir dosyanın tam yolunu almak için bu üye işlevini çağırın.

```
virtual CString GetFilePath() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dosyanın tam yolu.

### <a name="remarks"></a>Açıklamalar

Örneğin, çağırdığınızda `GetFilePath` kullanıcıya dosyası hakkında bir ileti oluşturmak için `c:\windows\write\myfile.wri`, dosya yolu `c:\windows\write\myfile.wri`, döndürülür.

Yalnızca dosya adını döndürmek için (`myfile.wri`), çağrı [GetFileName](#getfilename). Dosyanın başlığı döndürülecek (`myfile`), çağrı [GetFileTitle](#getfiletitle).

### <a name="example"></a>Örnek

Örneğin bakın [GetFileName](#getfilename).

##  <a name="getfiletitle"></a>  CFile::GetFileTitle

(Görünen ad) dosyası için dosya başlık almak için bu üye işlevini çağırın.

```
virtual CString GetFileTitle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan dosyanın başlığı.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı [GetFileTitle](/windows/desktop/api/commdlg/nf-commdlg-getfiletitlea) dosyanın başlığı alınacak. Başarılı olursa, yöntem sistem dosya adı kullanıcıya göstermek için kullanacağınız bir dize döndürür. Aksi takdirde, yöntemi çağıran [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) (dosya uzantısı dahil), temel alınan dosyasının dosya adı alınamadı. Bu nedenle, dosya uzantısı her zaman döndürülen dosya başlık dizesini dahil edilmez. Daha fazla bilgi için [GetFileTitle](/windows/desktop/api/commdlg/nf-commdlg-getfiletitlea) ve [PathFindFileName](/windows/desktop/api/shlwapi/nf-shlwapi-pathfindfilenamea) Windows SDK.

Dosyanın adı dahil olmak üzere yolun tamamını döndürülecek çağrı [GetFilePath](#getfilepath). Yalnızca dosya adını döndürmek için çağrı [GetFileName](#getfilename).

### <a name="example"></a>Örnek

Örneğin bakın [GetFileName](#getfilename).

##  <a name="getlength"></a>  CFile::GetLength

Dosyanın bayt cinsinden geçerli mantıksal uzunluğunu alır.

```
virtual ULONGLONG GetLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya uzunluğu.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]

##  <a name="getposition"></a>  CFile::GetPosition

Geçerli değerini yapılan sonraki çağrılar kullanılabilir dosya işaretçisini alır `Seek`.

```
virtual ULONGLONG GetPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dosya işaretçisi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]

##  <a name="getstatus"></a>  CFile::GetStatus

Bu yöntem, ilgili durum bilgilerini alır. bir verilen `CFile` nesne örneği ya da belirtilen dosya yolu.

```
BOOL GetStatus(CFileStatus& rStatus) const;

static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*rStatus*<br/>
Bir kullanıcı tarafından sağlanan başvuru `CFileStatus` durum bilgilerini alacak yapısı. `CFileStatus` Yapısının aşağıdaki alanlar:

- `CTime m_ctime` Dosyanın oluşturulduğu saat ve tarihi.

- `CTime m_mtime` Tarih ve dosyanın son değiştirilme saati.

- `CTime m_atime` Tarih ve okumak için dosyanın son erişilme zamanı.

- `ULONGLONG m_size` Dosyanın bayt DIR komutu tarafından belirlendiği şekilde, mantıksal boyutu.

- `BYTE m_attribute` Dosya özniteliği baytı.

- `char m_szFullName[_MAX_PATH]` Windows karakter kümesindeki mutlak dosya adı.

*lpszFileName*<br/>
Windows karakter dizesindeki, diğer bir deyişle istenen dosyanın yolunu ayarlayın. Göreli veya mutlak yol olabilir veya bir ağ yolu adı içerebilir.

*pTM*<br/>
CAtlTransactionManager nesne işaretçisi

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dosya durum bilgilerini başarıyla aldı TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Statik olmayan sürümü `GetStatus` ilişkili açık dosya durumu bilgilerini alır verilen `CFile` nesne.  Statik sürümünü `GetStatus` dosyayı açmaya gerek kalmadan belirtilen dosya yolundan dosya durumunu alır. Bu, bir dosyanın varlığını ve erişim hakları test edilmesi için yararlıdır.

`m_attribute` Üyesi `CFileStatus` yapısı dosya özniteliği kümesine başvuruyor. `CFile` Sağlar sınıfını **özniteliği** dosya öznitelikleri sembolik olarak belirtilebilir bu nedenle sabit listesi türü:

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

##  <a name="hfilenull"></a>  CFile::hFileNull

Geçerli bir dosya tanıtıcısını için varlığını belirler `CFile` nesne.

```
static AFX_DATA const HANDLE hFileNull;
```

### <a name="remarks"></a>Açıklamalar

Bu sabitin belirlemek için kullanılan `CFile` nesnesi geçerli bir dosya tanıtıcısını sahiptir.

Aşağıdaki örnek, bu işlemi göstermektedir:

[!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]

##  <a name="lockrange"></a>  CFile::LockRange

Açık bir dosya içinde bir dosya zaten kilitlenmişse, bir özel durum bayt aralığı kilitler.

```
virtual void LockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Parametreler

*dwPos*<br/>
Kilitlemek için bayt aralığı başlangıcı bayt uzaklığı.

*dwCount*<br/>
Aralığın kilitlemek için bayt sayısı.

### <a name="remarks"></a>Açıklamalar

Bir dosyadaki baytları kilitleme erişim için bu baytlardan başka işlemler tarafından engeller. Bir dosyanın birden fazla bölgeye kilitleyebilirsiniz ancak çakışan bölge izin verilir.

Bölge kilidini kaldırdığında kullanarak `UnlockRange` üye işlevi, bayt aralığı tam olarak daha önce kilitli olan bölge gelmelidir. `LockRange` İşlevi, bitişik bölgeleri birleştirme değil; kilitli iki bölgeleri bitişikse, her bölgede ayrı olarak kilidini açmanız gerekir.

> [!NOTE]
>  Bu işlev için kullanılabilir değil `CMemFile`-türetilmiş sınıf.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

##  <a name="m_hfile"></a>  CFile::m_hFile

Açık bir dosya için işletim sistemi dosya tanıtıcısı içerir.

```
HANDLE m_hFile;
```

### <a name="remarks"></a>Açıklamalar

`m_hFile` UINT türünde genel bir değişkendir. İçerdiği `CFile::hFileNull` (işletim sistemi-bağımsız boş dosya göstergesi) tanıtıcı atanmamış durumunda.

Kullanım `m_hFile` önerilmez çünkü üyenin anlamı türetilmiş sınıfa bağlıdır. `m_hFile` sınıfını kullanan bir ortak üye dönüştürülmesi destekleyen kolaylık sağlamak için yapılır.

##  <a name="m_ptm"></a>  CFile::m_pTM

İşaretçi bir `CAtlTransactionManager` nesne.

```
CAtlTransactionManager* m_pTM;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="open"></a>  CFile::Open

Fazla Yüklendi. `Open` Varsayılan değer ile kullanılmak üzere tasarlanmış `CFile` Oluşturucusu.

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
İstenen dosya yolu bir dize. Yol göreli veya mutlak bir ağ adı (UNC) olabilir.

*nOpenFlags*<br/>
Dosya Paylaşımı ve erişimi modu tanımlar UINT. Bu dosyayı açarken gerçekleştirilecek eylemi belirtir. Seçenekler bit düzeyinde OR kullanarak birleştirebilir ( **&#124;** ) işleci. Bir erişim izni ve bir paylaşım seçeneği gereklidir; `modeCreate` ve `modeNoInherit` modlarıdır isteğe bağlı. Bkz: [CFile](#cfile) modu seçeneklerin bir listesi için oluşturucu.

*pError*<br/>
Başarısız bir işlemin durumunu alacak varolan bir dosyanın özel durum nesnesine bir işaretçi.

*pTM*<br/>
CAtlTransactionManager nesne işaretçisi

### <a name="return-value"></a>Dönüş Değeri

Açma işlemi başarılı olursa sıfır dışı; Aksi durumda 0. *PError* parametresi, yalnızca 0 döndürülürse anlamlı.

### <a name="remarks"></a>Açıklamalar

İki işlev hata normal, beklenen bir koşulu bulunduğu bir dosya açmak için "güvenli" bir yöntem oluşturur.

Sırada `CFile` Oluşturucusu bir özel durum hata koşulu oluşturur `Open` hata koşulları için FALSE döndürür. `Open` yine de başlatabilirsiniz bir [CFileException](../../mfc/reference/cfileexception-class.md) hata ancak tanımlamak için nesne. Sağlamazsanız *pError* parametresi veya NULL geçirmek *pError*, `Open` false değerini döndürür ve değil throw bir `CFileException`. Varolan bir işaretçi geçirirseniz `CFileException`, ve `Open` bir hatayla karşılaşıyorsa, işlev doldurur, bu hatayı açıklayan bilgileri. Büyük/küçük harf ne olacak içinde `Open` bir özel durum.

Aşağıdaki tablo olası sonuçlarını açıklar `Open`.

|`pError`|Hatayla karşılaşıldı|Dönüş değeri|CFileException içeriği|
|--------------|------------------------|------------------|----------------------------|
|NULL|Hayır|TRUE|yok|
|PTR `CFileException`|Hayır|TRUE|değişmedi|
|NULL|Evet|FALSE|yok|
|PTR `CFileException`|Evet|FALSE|hatayı açıklamak için başlatıldı|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]

[!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]

##  <a name="operator_handle"></a>  CFile::operator TANITICISI

İşleyici geçirmek için bu işleci kullanın. bir `CFile` işlevler gibi nesne [ReadFileEx](/windows/desktop/api/fileapi/nf-fileapi-readfileex) ve [GetFileTime](/windows/desktop/api/fileapi/nf-fileapi-getfiletime) , beklediğiniz bir `HANDLE`.

```
operator HANDLE() const;
```

##  <a name="read"></a>  CFile::Read

Bir arabelleğine ilişkili dosyadan verileri okur `CFile` nesne.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Dosyadan okunan veriler alacak olan kullanıcı tarafından sağlanan arabellek için işaretçi.

*nCount*<br/>
Dosyadan okunacak bayt sayısı. Metin modunda dosyalar için satır başı satır besleme çiftleri tek karakter olarak sayılır.

### <a name="return-value"></a>Dönüş Değeri

Arabelleğe aktarılan bayt sayısı. Tüm unutmayın `CFile` sınıflar, dönüş değeri olabilir küçüktür *nCount* , dosya sonuna ulaşıldı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]

Başka bir örnek için bkz. [CFile::Open](#open).

##  <a name="remove"></a>  CFile::Remove

Bu statik işlev yolu tarafından belirtilen dosyayı siler.

```
static void PASCAL Remove(
    LPCTSTR lpszFileName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
İstenen dosya yolu bir dize. Yol göreli veya mutlak olabilir ve bir ağ adı içermelidir.

*pTM*<br/>
CAtlTransactionManager nesne işaretçisi

### <a name="remarks"></a>Açıklamalar

Bir dizin kaldırmaz.

`Remove` Üye işlevi bağlı dosya açık değilse veya dosya kaldırdıysanız bir özel durum oluşturur. Bu, DEL komuta denktir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]

##  <a name="rename"></a>  CFile::Rename

Bu statik işlev, belirtilen dosyayı yeniden adlandırır.

```
static void PASCAL Rename(
    LPCTSTR lpszOldName,
    LPCTSTR lpszNewName,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszOldName*<br/>
Eski yolu.

*lpszNewName*<br/>
Yeni yolu.

*pTM*<br/>
CAtlTransactionManager nesne işaretçisi

### <a name="remarks"></a>Açıklamalar

Dizinleri yeniden adlandırılamaz. Bu, REN komuta denktir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]

##  <a name="seek"></a>  CFile::Seek

Dosya işaretçisini de açık bir dosyayı yeniden konumlandırır.

```
virtual ULONGLONG Seek(
LONGLONG lOff,
UINT nFrom);
```

### <a name="parameters"></a>Parametreler

*lOff*<br/>
Dosya işaretçisini taşımak için bayt sayısı. Pozitif değerler, dosya işaretçisini dosyanın sonuna doğru taşır. negatif değerler dosya işaretçisini dosyanın başlangıcına doğru taşıyın.

*nFrom*<br/>
Gelen arama konumu. Olası değerler için Açıklamalar bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa dosya işaretçisi konumunu; Aksi takdirde, dönüş değeri tanımlı değil ve bir işaretçi bir `CFileException` özel durumu oluşturulur.

### <a name="remarks"></a>Açıklamalar

İçin olası değerler aşağıdaki tabloda *nFrom* parametresi.

|Değer|Açıklama|
|-----------|-----------------|
|`CFile::begin`|Dosyanın başlangıcından isteyin.|
|`CFile::current`|Dosya işaretçisini geçerli konumdan isteyin.|
|`CFile::end`|Dosyanın sonundan isteyin.|

Bir dosya açıldığında, dosya işaretçisini 0'da, dosya başı konumlandırıldı.

Dosya işaretçisini dosyanın sonundan bir konuma ayarlayabilirsiniz. Bunu yaparsanız, dosyaya yazmak kadar dosya boyutunu artırmaz.

Özel durum işlendikten sonra bu yöntem için özel durum işleyicisi özel durum nesnesi silmeniz gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]

##  <a name="seektobegin"></a>  CFile::SeekToBegin

Dosya işaretçisini dosyanın başına ayarlar.

```
void SeekToBegin();
```

### <a name="remarks"></a>Açıklamalar

`SeekToBegin()` eşdeğerdir `Seek( 0L, CFile::begin )`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

##  <a name="seektoend"></a>  CFile::SeekToEnd

Dosya işaretçisini dosyanın mantıksal sonuna ayarlar.

```
ULONGLONG SeekToEnd();
```

### <a name="return-value"></a>Dönüş Değeri

Dosyanın bayt cinsinden uzunluğu.

### <a name="remarks"></a>Açıklamalar

`SeekToEnd()` eşdeğerdir `CFile::Seek( 0L, CFile::end )`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]

##  <a name="setfilepath"></a>  CFile::SetFilePath

Dosyasının yolunu belirtmek için bu işlevi çağırın. Örneğin, bir dosyanın yolunu ne zaman kullanılabilir değilse, bir [CFile](../../mfc/reference/cfile-class.md) nesnesi oluşturulduğunda, çağrı `SetFilePath` sağlamayı.

```
virtual void SetFilePath(LPCTSTR lpszNewName);
```

### <a name="parameters"></a>Parametreler

*lpszNewName*<br/>
Yeni yol belirten bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> `SetFilePath` değil dosyasını açın veya bir dosya oluşturun; yalnızca ilişkilendirir `CFile` sonra kullanılabilir bir yol adına sahip bir nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]

##  <a name="setlength"></a>  CFile::SetLength

Dosyayı değiştirmek için bu işlevi çağırın.

```
virtual void SetLength(ULONGLONG dwNewLen);
```

### <a name="parameters"></a>Parametreler

*dwNewLen*<br/>
İstenen dosyanın bayt cinsinden uzunluğu. Bu değer, geçerli dosya uzunluğu daha büyük veya küçük olabilir. Dosya genişletilmiş veya uygun şekilde kesildi.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  İle `CMemFile`, bu işlevin throw bir `CMemoryException` nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]

##  <a name="setstatus"></a>  CFile::SetStatus

Bu dosya konumu ile ilişkili dosya durumunu ayarlar.

```
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,
    const CFileStatus& status,
    CAtlTransactionManager* pTM = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszFileName*<br/>
İstenen dosya yolu bir dize. Yol göreli veya mutlak olabilir ve bir ağ adı içermelidir.

*Durumu*<br/>
Yeni durum bilgilerini içeren arabellek. Çağrı `GetStatus` imzalanmak üzere bir üye işlevi `CFileStatus` geçerli değerlerle yapılandırın ve ardından gerekli değişiklikleri yapın. Bir değer 0 ise, karşılık gelen durum öğesi güncelleştirilmez. Bkz: [GetStatus](#getstatus) üye işlevi bir açıklaması için `CFileStatus` yapısı.

*pTM*<br/>
CAtlTransactionManager nesne işaretçisi

### <a name="remarks"></a>Açıklamalar

Değiştirme saati ayarlamak üzere `m_mtime` alanını *durumu*.

Çağrısı yaptığınızda lütfen unutmayın `SetStatus` yalnızca dosya özniteliklerini değiştirme girişimi ve `m_mtime` dosya durumu yapısı üyesi sıfır olmayan, öznitelikler (damga üzerinde yan etkileri olabilir zamanı değiştirme da etkilenebilir öznitelikler). Yalnızca dosya özniteliklerini değiştirmek istiyorsanız, öncelikle ayarlamanız `m_mtime` sıfır ve ardından bir çağrı yapmak için dosya durum yapısı üyesi `SetStatus`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]

##  <a name="unlockrange"></a>  CFile::UnlockRange

Açık bir dosya bir bayt aralığı kilidini açar.

```
virtual void UnlockRange(
    ULONGLONG dwPos,
    ULONGLONG dwCount);
```

### <a name="parameters"></a>Parametreler

*dwPos*<br/>
Kilidini açmak için bayt aralığı başlangıcı bayt uzaklığı.

*dwCount*<br/>
Kilidini açmak için aralıktaki bayt sayısı.

### <a name="remarks"></a>Açıklamalar

Açıklamasını görmek [LockRange](#lockrange) Ayrıntılar için üye işlevi.

> [!NOTE]
>  Bu işlev için kullanılabilir değil `CMemFile`-türetilmiş sınıf.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]

##  <a name="write"></a>  CFile::Write

Veri arabellek ile ilişkili bir dosyaya yazar `CFile` nesne.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Dosyaya yazılacak veriler içeren kullanıcı tarafından sağlanan arabellek için işaretçi.

*nCount*<br/>
Arabellekteki aktarılacak bayt sayısı. Metin modunda dosyalar için satır başı satır besleme çiftleri tek karakter olarak sayılır.

### <a name="remarks"></a>Açıklamalar

`Write` yanıt olarak disk dolu koşulu dahil olmak üzere çeşitli koşullar, özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]

Ayrıca, örnekler için bkz. [CFile::CFile](#cfile) ve [CFile::Open](#open).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CStdioFile Sınıfı](../../mfc/reference/cstdiofile-class.md)<br/>
[CMemFile Sınıfı](../../mfc/reference/cmemfile-class.md)
