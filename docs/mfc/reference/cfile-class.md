---
title: "CFile sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4db8a7ee97c414a7775df393d419c7d12d61cdbf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[CFile::CFile](#cfile)|Oluşturan bir `CFile` nesne yolu veya dosya tanıtıcısı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFile::Abort](#abort)|Tüm uyarıları ve hataları yoksayma dosyayı kapatır.|  
|[CFile::Close](#close)|Bir dosyayı kapatır ve nesneyi siler.|  
|[CFile::Duplicate](#duplicate)|Bu dosyada göre yinelenen bir nesne oluşturur.|  
|[CFile::Flush](#flush)|Henüz yazılacak herhangi bir veri aktarır.|  
|[CFile::GetFileName](#getfilename)|Seçilen dosya adını alır.|  
|[CFile::GetFilePath](#getfilepath)|Seçilen dosya tam dosya yolunu alır.|  
|[CFile::GetFileTitle](#getfiletitle)|Seçilen dosya başlığını alır.|  
|[CFile::GetLength](#getlength)|Dosya uzunluğunu alır.|  
|[CFile::GetPosition](#getposition)|Geçerli dosya işaretçisini alır.|  
|[CFile::GetStatus](#getstatus)|Durum açık dosyanın veya statik sürümünde alır, belirtilen dosya (statik, sanal işlev) durumunu alır.|  
|[CFile::LockRange](#lockrange)|Bir dosyada bir bayt aralığı kilitler.|  
|[CFile::Open](#open)|Güvenli bir şekilde bir dosya bir hata test etme seçeneği ile açılır.|  
|[CFile::Read](#read)|Geçerli dosya konumundaki bir dosyadan (arabellekten çıkarılan) verileri okur.|  
|[CFile::Remove](#remove)|Belirtilen dosya (statik işlevi) siler.|  
|[CFile::Rename](#rename)|Belirtilen dosya (statik işlevi) yeniden adlandırır.|  
|[CFile::Seek](#seek)|Geçerli dosya işaretçisini yerleştirir.|  
|[CFile::SeekToBegin](#seektobegin)|Geçerli dosya işaretçisini dosyasının başında yerleştirir.|  
|[CFile::SeekToEnd](#seektoend)|Geçerli dosya işaretçisini dosyanın sonunda yerleştirir.|  
|[CFile::SetFilePath](#setfilepath)|Seçili dosyanın tam dosya yolunu ayarlar.|  
|[CFile::SetLength](#setlength)|Dosya uzunluğu değiştirir.|  
|[CFile::SetStatus](#setstatus)|Belirtilen dosya (statik, sanal işlev) durumunu ayarlar.|  
|[CFile::UnlockRange](#unlockrange)|Bir dosyada bir bayt aralığı kilidini açar.|  
|[CFile::Write](#write)|(Arabellekten çıkarılan) verilerini bir dosyada geçerli dosya konumuna yazma.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFile::operator TANITICISI](#operator_handle)|İçin bir tanıtıcı bir `CFile` nesnesi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFile::hFileNull](#hfilenull)|Belirler `CFile` nesnesi geçerli bir tanıtıcı sahiptir.|  
|[CFile::m_hFile](#m_hfile)|Genellikle işletim sistemi dosya işleci içerir.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFile::m_pTM](#m_ptm)|İşaretçi `CAtlTransactionManager` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Doğrudan arabellekten çıkarılan, ikili disk giriş/çıkış hizmetleri sağlar ve metin dosyaları ve bellek dosyalarını türetilmiş sınıflarının üzerinden dolaylı olarak destekler. `CFile`ile birlikte çalışır `CArchive` Microsoft Foundation Class nesneleri serileştirmek desteklemek için sınıf.  
  
 Bu sınıf ve türetilmiş sınıflarının arasındaki hiyerarşik ilişkiyi biçimli aracılığıyla tüm dosya nesneler üzerinde çalışması, program sağlar `CFile` arabirimi. Bellek dosyası, örneğin, bir disk dosyası gibi davranır.  
  
 Kullanım `CFile` ve türetilmiş sınıflarının genel amaçlı disk g/ç için. Kullanım `ofstream` veya diğer Microsoft iostream sınıfları için bir disk dosyası gönderilen biçimlendirilmiş metin.  
  
 Normalde, bir disk dosyası otomatik olarak açılan `CFile` yapım ve üzerinde kapalı yok etme. Statik üye işlevleri, bir dosyanın durumuna dosyayı açmadan sorgulayın izin verir.  
  
 Kullanma hakkında daha fazla bilgi için `CFile`, makalelerine bakın [MFC'deki dosyalar](../../mfc/files-in-mfc.md) ve [dosya işleme](../../c-runtime-library/file-handling.md) içinde *çalışma zamanı kitaplığı başvurusu*.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="abort"></a>CFile::Abort  
 Bu nesneyle ilişkili dosyayı kapatır ve dosyayı okuma veya yazma için kullanılabilir hale getirir.  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya nesnesi yok etme önce kapatılmamış, yıkıcı sizin için kapatılır.  
  
 Özel durumlar, işlerken `CFile::Abort` farklıdır `CFile::Close` iki önemli şekilde. İlk olarak, **Abort** işlevi değil throw bir özel durum hatalarında hataları tarafından göz ardı edilir çünkü **Abort**. İkinci, **Abort** almayacak **ASSERT** dosya açılmamış olan veya daha önce kapatıldı.  
  
 Kullandıysanız **yeni** ayırmak için `CFile` nesne yığında sonra dosya kapattıktan sonra silmeniz gerekir. **Abort** ayarlar `m_hFile` için `CFile::hFileNull`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#5](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_1.cpp)]  
  
##  <a name="cfile"></a>CFile::CFile  
 Oluşturur ve başlatır bir `CFile` nesnesi.  
  
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
 `hFile`  
 Eklemek için bir dosya tanıtıcısı `CFile` nesnesi.  
  
 `lpszFileName`  
 Bir dosya iliştirmek için göreli veya tam yolunu `CFile` nesnesi.  
  
 `nOpenFlags`  
 Bit düzeyinde bileşimini (veya) belirtilen dosya için dosya erişim seçenekleri. Olası seçenekler için Açıklamalar bölümüne bakın.  
  
 `pTM`  
 CAtlTransactionManager nesnesine işaretçi  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki beş tablolar için olası seçenekler listesinde `nOpenFlags` parametresi.  
  
 Aşağıdaki dosya erişim modu seçeneklerden yalnızca birini seçin. Varsayılan dosya erişim modu `CFile::modeRead`, hangi salt okunur.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`CFile::modeRead`|Yalnızca istekleri okuma erişimi.|  
|`CFile::modeWrite`|Yalnızca istekleri yazma erişimi.|  
|`CFile::modeReadWrite`|İstekleri okuma ve yazma erişimi.|  
  
 Karakter modu şunlardan birini seçin.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`CFile::typeBinary`|İkili mod (yalnızca türetilmiş sınıflarda kullanılır) ayarlar.|  
|`CFile::typeText`|(Yalnızca türetilmiş sınıflarda kullanılır) satır başı satır besleme çiftleri için özel işlem metin moduyla ayarlar.|  
|`CFile::typeUnicode`|Unicode modu (yalnızca türetilmiş sınıflarda kullanılır) ayarlar. Uygulama bir Unicode yapılandırmasında yapılandırıldığında metin Unicode biçiminde dosyasına yazılır. Hiçbir BOM dosyasına yazılır.|  
  
 Aşağıdaki dosya paylaşım modu seçeneklerden yalnızca birini seçin. Varsayılan dosya paylaşım modu `CFile::shareExclusive`, özel olduğu.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`CFile::shareDenyNone`|Paylaşım kısıtlama yoktur.|  
|`CFile::shareDenyRead`|Diğer tüm kullanıcılar için okuma erişimi engeller.|  
|`CFile::shareDenyWrite`|Diğer tüm kullanıcılar için yazma erişimini engeller.|  
|`CFile::shareExclusive`|Okuma ve yazma erişimi diğerlerini reddeder.|  
  
 İlk veya her ikisi de aşağıdaki dosya oluşturma modu seçeneklerden birini seçin. Varsayılan oluşturma modu `CFile::modeNoTruncate`, açık var olduğu.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`CFile::modeCreate`|Hiçbir dosya varsa, yeni bir dosya oluşturur.; Dosya zaten mevcutsa [CFileException](../../mfc/reference/cfileexception-class.md) tetiklenir.|  
|`CFile::modeNoTruncate`|Hiçbir dosya varsa, yeni bir dosya oluşturur; Dosya zaten mevcutsa, aksi takdirde, bağlı olduğu `CFile` nesnesi.|  
  
 Önbelleğe alma seçeneklerini açıklandığı gibi aşağıdaki dosyayı seçin. Varsayılan olarak, sistem bir seçenek olarak kullanılabilir değil düzeni önbelleğe alma genel amaçlı kullanır.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`CFile::osNoBuffer`|Sistem, dosya için bir ara önbelleği kullanmaz. Bu seçenek aşağıdaki 2 seçenek iptal eder.|  
|`CFile::osRandomAccess`|Dosya önbelleği rastgele erişim için optimize edilmiştir. Bu seçenek ve sıralı Tarama seçeneğini kullanmayın.|  
|`CFile::osSequentialScan`|Dosya önbelleği sıralı erişim için optimize edilmiştir. Bu seçenek ve rasgele erişim seçeneğini kullanmayın.|  
|`CFile::osWriteThrough`|Gecikme olmadan gerçekleştirilen işlemler yazma.|  
  
 Dosya tanıtıcısı devralınan gelen önlemek için aşağıdaki güvenlik seçeneği seçin. Varsayılan olarak, yeni alt işlemlere dosya tanıtıcısı kullanabilirsiniz.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`CFile::modeNoInherit`|Herhangi bir alt işlem dosya tanıtıcısı kullanmalarını engeller.|  
  
 Varsayılan Oluşturucu üyeleri başlatır, ancak bir dosyaya eklemez `CFile` nesnesi. Bu oluşturucu kullanıldıktan sonra IStream [CFile::Open](#open) bir dosyayı açın ve kendisine eklemek için yöntemi `CFile` nesnesi.  
  
 Yapıcı, bir parametre ile üyeleri başlatır ve var olan bir dosyaya ekler `CFile` nesnesi.  
  
 İki parametrelerle Oluşturucu üyeleri başlatır ve belirtilen dosyayı açmaya çalışır. Bu oluşturucu başarıyla belirtilen dosya açılırsa, dosya bağlı `CFile` nesne; Aksi takdirde, bu oluşturucuyu gösteren bir işaretçi oluşturur bir `CInvalidArgException` nesnesi. Özel durumları işleme hakkında daha fazla bilgi için bkz: [özel durumları](../../mfc/exception-handling-in-mfc.md).  
  
 Varsa bir `CFile` nesnesi başarılı bir şekilde belirtilen bir dosya açıldığında, bu dosyayı otomatik olarak zaman kapanacak `CFile` nesne yok edilir; Aksi takdirde, için artık bağlandıktan sonra dosyayı açıkça kapatmalısınız `CFile` nesnesi.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösteren bir `CFile`.  
  
 [!code-cpp[NVC_MFCFiles#4](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_2.cpp)]  
  
##  <a name="close"></a>CFile::Close  
 Bu nesneyle ilişkili dosyayı kapatır ve dosyayı okuma veya yazma için kullanılabilir hale getirir.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya nesnesi yok etme önce kapatılmamış, yıkıcı sizin için kapatılır.  
  
 Kullandıysanız **yeni** ayırmak için `CFile` nesne yığında sonra dosya kapattıktan sonra silmeniz gerekir. **Kapat** ayarlar `m_hFile` için `CFile::hFileNull`.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CFile::CFile](#cfile).  
  
##  <a name="duplicate"></a>CFile::Duplicate  
 Yinelenen yapıları `CFile` nesne belirli bir dosya için.  
  
```  
virtual CFile* Duplicate() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yinelenen bir işaretçi `CFile` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu C çalışma zamanı işlevine eşdeğerdir `_dup`.  
  
##  <a name="flush"></a>CFile::Flush  
 Dosyasına yazılacak olan dosya arabelleği kalan herhangi bir veri zorlar.  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanımını `Flush` , temizleme garanti etmez `CArchive` arabellek. Bir arşiv kullanıyorsanız, çağrı [CArchive::Flush](../../mfc/reference/carchive-class.md#flush) ilk.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CFile::SetFilePath](#setfilepath).  
  
##  <a name="getfilename"></a>CFile::GetFileName  
 Belirtilen dosya adını almak için bu üye işlevini çağırın.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dosyanın adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdığınızda Örneğin, `GetFileName` dosyası hakkında kullanıcıya bir ileti oluşturmak için `c:\windows\write\myfile.wri`, filename `myfile.wri`, döndürülür.  
  
 Yolun tamamını dosyasının adı dahil olmak üzere döndürmek için çağrı [GetFilePath](#getfilepath). Dosya başlığı döndürülecek ( `myfile`), çağrı [GetFileTitle](#getfiletitle).  
  
### <a name="example"></a>Örnek  
 Bu kod parçası, sistem açar. WINDOWS dizinindeki INI dosyası. Bulunursa, örnek adı ve yolu ve başlık, çıkış altında gösterildiği gibi yazdırılır varsa:  
  
 [!code-cpp[NVC_MFCFiles#6](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_3.cpp)]  
  
##  <a name="getfilepath"></a>CFile::GetFilePath  
 Belirtilen bir dosyanın tam yolunu almak için bu üye işlevini çağırın.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dosyasının tam yolu.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdığınızda Örneğin, `GetFilePath` dosyası hakkında kullanıcıya bir ileti oluşturmak için `c:\windows\write\myfile.wri`, dosya yolunu `c:\windows\write\myfile.wri`, döndürülür.  
  
 Yalnızca dosya adını döndürmek için ( `myfile.wri`), çağrı [GetFileName](#getfilename). Dosya başlığı döndürülecek ( `myfile`), çağrı [GetFileTitle](#getfiletitle).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetFileName](#getfilename).  
  
##  <a name="getfiletitle"></a>CFile::GetFileTitle  
 Dosyası için dosya başlık (görünen adı) almak için bu üye işlevini çağırın.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel alınan dosya başlığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır [GetFileTitle](http://msdn.microsoft.com/library/windows/desktop/ms646924) dosya başlığı almak için. Başarılı olursa, yöntem sistem kullanıcıya dosya adını görüntülemek için kullanacağınız dize döndürür. Aksi takdirde yöntemini çağırır [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) (dosya uzantısı dahil), temel alınan dosyasının dosya adı alınamadı. Bu nedenle, dosya adı uzantısı her zaman döndürülen dosya başlık dizesinde dahil edilmez. Daha fazla bilgi için bkz: [GetFileTitle](http://msdn.microsoft.com/library/windows/desktop/ms646924) ve [PathFindFileName](http://msdn.microsoft.com/library/windows/desktop/bb773589) Windows SDK'sındaki.  
  
 Yolun tamamını dosyasının adı dahil olmak üzere döndürmek için çağrı [GetFilePath](#getfilepath). Yalnızca dosya adını döndürmek için arama [GetFileName](#getfilename).  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [GetFileName](#getfilename).  
  
##  <a name="getlength"></a>CFile::GetLength  
 Dosyanın bayt cinsinden geçerli mantıksal uzunluğunu alır.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dosya uzunluğu.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#7](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_4.cpp)]  
  
##  <a name="getposition"></a>CFile::GetPosition  
 Sonraki çağrılar kullanılabilir dosya işaretçisini geçerli değeri elde `Seek`.  
  
```  
virtual ULONGLONG GetPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dosya işaretçisini.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#8](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_5.cpp)]  
  
##  <a name="getstatus"></a>CFile::GetStatus  
 Bu yöntem ile ilgili durum bilgilerini alır bir verilen `CFile` nesne örneği veya belirtilen dosya yolu.  
  
```  
BOOL GetStatus(CFileStatus& rStatus) const;  
  
static BOOL PASCAL GetStatus(
    LPCTSTR lpszFileName,  
    CFileStatus& rStatus,
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `rStatus`  
 Kullanıcı tarafından sağlanan başvuru **CFileStatus** durum bilgileri alacak yapısı. **CFileStatus** yapısının aşağıdaki alanlar:  
  
- **CTime m_ctime** dosyanın oluşturulduğu tarih ve saat.  
  
- **CTime m_mtime** dosyanın son değiştirilme saati ve tarihi.  
  
- **CTime m_atime** okumak için dosyaya son erişilen saat ve tarihi.  
  
- **ULONGLONG m_size** DIR komutu tarafından bildirilen bayt cinsinden dosyasının mantıksal boyutu.  
  
- **BAYT m_attribute** dosyasının özniteliği bayt.  
  
- **m_szFullName [_MAX_PATH] char** Windows karakter kümesinde mutlak dosya adı.  
  
 `lpszFileName`  
 Windows karakter dizesinde diğer bir deyişle istenen dosyanın yolunu ayarlama. Göreli veya mutlak bir yol olabilir veya bir ağ yolu adı içerebilir.  
  
 `pTM`  
 CAtlTransactionManager nesnesine işaretçi  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DOĞRU** belirtilen dosya için durum bilgisi, başarılı bir şekilde elde edilen Aksi takdirde **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Statik olmayan sürümü **GetStatus** durum bilgileri ile ilişkili açık dosyanın alır verilen `CFile` nesnesi.  Statik sürümü **GetStatus** dosyayı açmaya gerek kalmadan verilen dosya yolundan dosya durumunu alır. Bu, bir dosyanın varlığı ve erişim haklarını test etmek için kullanışlıdır.  
  
 **M_attribute** üyesi **CFileStatus** yapısı dosya özniteliği kümesine başvuruyor. `CFile` SAX **özniteliği** numaralandırma, dosya öznitelikleri sembolik olarak belirtilmesi nedenle yazın:  
  
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
  
##  <a name="hfilenull"></a>CFile::hFileNull  
 İçin geçerli bir dosya tanıtıcısı varlığını belirler `CFile` nesnesi.  
  
```  
static AFX_DATA const HANDLE hFileNull;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sabit belirlemek için kullanılan `CFile` nesnesi geçerli bir dosya tanıtıcısı sahiptir.  
  
 Aşağıdaki örnek, bu işlemi gösterir:  
  
 [!code-cpp[NVC_MFCFiles#22](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_7.cpp)]  
  
##  <a name="lockrange"></a>CFile::LockRange  
 Açık bir dosyanın dosya zaten kilitliyse bir özel durum atma bayt aralığı kilitler.  
  
```  
virtual void LockRange(
    ULONGLONG dwPos,  
    ULONGLONG dwCount);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwPos`  
 Kilitlemek için bayt aralığı başlangıcı bayt uzaklığı.  
  
 `dwCount`  
 Kilitlemek için aralıktaki bayt sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dosyada baytları kilitleme erişimi başka işlemler tarafından bu bayt engeller. Bir dosyanın birden fazla bölge kilitleyebilirsiniz ancak hiç çakışan bölge izin verilir.  
  
 Bölge kilidini kullandığınızda `UnlockRange` üye işlevi bayt aralığı gerekir karşılık gelen daha önce kilitli olan bölge tam olarak. `LockRange` İşlevi bitişik bölgeler birleştirme değil; iki kilitli bölgeler bitişikse, her bölge ayrı olarak kilidini açmanız gerekir.  
  
> [!NOTE]
>  Bu işlev için kullanılabilir değil `CMemFile`-türetilmiş sınıf.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]  
  
##  <a name="m_hfile"></a>CFile::m_hFile  
 Açık bir dosyayı işletim sistemi dosya işleci içeriyor.  
  
```  
HANDLE m_hFile;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 `m_hFile`tür genel bir değişkendir **UINT**. İçerdiği `CFile::hFileNull` (bir işletim sistemi-bağımsız boş dosya gösterge) tanıtıcı atanmamıştır durumunda.  
  
 Kullanımı `m_hFile` üyenin anlamı türetilmiş sınıf üzerinde bağımlı olduğu için önerilmez. `m_hFile`sınıfını kullanmak ortak bir üye nonpolymorphic destekleyen kolaylık sağlamak için yapılır.  
  
##  <a name="m_ptm"></a>CFile::m_pTM  
 İşaretçi bir `CAtlTransactionManager` nesnesi.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="open"></a>CFile::Open  
 Fazla Yüklendi. **Açık** varsayılan ile kullanılmak üzere tasarlanmış `CFile` Oluşturucusu.  
  
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
 `lpszFileName`  
 İstenen dosyanın yolu olan bir dize. Göreli, mutlak veya bir ağ adı (UNC) yolu olabilir.  
  
 `nOpenFlags`  
 A **UINT** dosya paylaşımı ve erişim modu tanımlar. Dosyayı açarken gerçekleştirilecek eylemi belirtir. Bit düzeyinde-OR kullanarak Seçenekleri birleştirebilirsiniz ( **&#124;** ) işleci. Bir erişim izni ve bir paylaşım seçeneği gereklidir; **modeCreate** ve **modeNoInherit** modları isteğe bağlıdır. Bkz: [CFile](#cfile) Oluşturucusu modu seçenekleri listesi.  
  
 `pError`  
 Bir işaretçi var olan bir dosya özel durumu nesneye başarısız bir işlemin durumunu alacak.  
  
 `pTM`  
 CAtlTransactionManager nesnesine işaretçi  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açık başarılı olduğunda sıfır olmayan; Aksi takdirde 0. `pError` Parametresi yalnızca 0 döndürülürse anlamlı.  
  
### <a name="remarks"></a>Açıklamalar  
 İki işlevler hata normal, beklenen bir durum olduğu bir dosyanın açılması için bir "safe" yöntem oluşturur.  
  
 Sırada `CFile` Oluşturucusu bir özel durum bir hata koşulu throw **açık** döndürülecek **FALSE** hata koşulları için. **Açık** hala başlatabilir bir [CFileException](../../mfc/reference/cfileexception-class.md) hata ancak açıklamak için nesne. Belirlemezseniz `pError` parametresi veya geçirirseniz **NULL** için `pError`, **açık** döndürülecek **FALSE** değil başlatıldıysa ve bir `CFileException`. Var olan bir işaretçi geçirirseniz `CFileException`, ve **açık** karşılaştığı hata işlevi doldurur, bu hatayı açıklayan bilgilerle. Servis talebi hiçbiri içinde **açık** bir özel durum.  
  
 Aşağıdaki tabloda olası sonuçları açıklanmaktadır **açık**.  
  
|`pError`|Hatayla karşılaşıldı|Dönüş değeri|CFileException içeriği|  
|--------------|------------------------|------------------|----------------------------|  
|**NULL**|Hayır|**TRUE**|yok|  
|PTR`CFileException`|Hayır|**TRUE**|Değişmedi|  
|**NULL**|Evet|**FALSE**|yok|  
|PTR`CFileException`|Evet|**FALSE**|hata açıklamak için başlatıldı|  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#13](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCFiles#14](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_10.cpp)]  
  
##  <a name="operator_handle"></a>CFile::operator TANITICISI  
 İçin bir tanıtıcı geçirmek için bu işleci kullanın bir `CFile` işlevler gibi nesne [ReadFileEx](http://msdn.microsoft.com/library/windows/desktop/aa365468) ve [GetFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724320) , beklediğiniz bir `HANDLE`.  
  
```  
operator HANDLE() const;  
```  
  
##  <a name="read"></a>CFile::Read  
 İle ilişkili dosyasından arabellek içine veri okuyan `CFile` nesnesi.  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpBuf`  
 Dosyadan okunan verileri almak için kullanıcı tarafından sağlanan arabellek işaretçi.  
  
 `nCount`  
 Dosyadan okunan bayt sayısı. Metin modunu dosyalar için satır başı satır besleme çiftleri tek karakter olarak sayılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arabelleğe aktarılan toplam bayt sayısı. Tüm unutmayın `CFile` sınıfları, dönüş değeri olabilir değerinden `nCount` varsa dosya sonuna ulaşıldı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#15](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_11.cpp)]  
  
 Başka bir örnek için bkz: [CFile::Open](#open).  
  
##  <a name="remove"></a>CFile::Remove  
 Bu statik işlev yolu tarafından belirtilen dosyayı siler.  
  
```  
static void PASCAL Remove(
    LPCTSTR lpszFileName, 
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFileName`  
 İstenen dosyanın yolu olan bir dize. Yolun göreli veya mutlak olabilir ve bir ağ adı içermelidir.  
  
 `pTM`  
 CAtlTransactionManager nesnesine işaretçi  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizin kaldırmaz.  
  
 **Kaldırmak** üye işlevi bağlı dosya açıksa veya dosya kaldırdıysanız bir özel durum oluşturur. Bu, DEL komutunu eşdeğerdir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#17](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_12.cpp)]  
  
##  <a name="rename"></a>CFile::Rename  
 Bu statik işlevi belirtilen dosyayı yeniden adlandırır.  
  
```  
static void PASCAL Rename(
    LPCTSTR lpszOldName,  
    LPCTSTR lpszNewName,  
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszOldName`  
 Eski yolu.  
  
 `lpszNewName`  
 Yeni yolu.  
  
 `pTM`  
 CAtlTransactionManager nesnesine işaretçi  
  
### <a name="remarks"></a>Açıklamalar  
 Dizinleri yeniden adlandırılamaz. Bu, REN komutu ile eşdeğerdir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#18](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_13.cpp)]  
  
##  <a name="seek"></a>CFile::Seek  
 Dosya işaretçisini açık bir dosyayı yeniden konumlandırır.  
  
```  
virtual ULONGLONG Seek(
LONGLONG lOff,  
UINT nFrom);
```  
  
### <a name="parameters"></a>Parametreler  
 `lOff`  
 Dosya işaretçisini taşımak için bayt sayısı. Pozitif değerler dosya işaretçisini dosyanın sonuna taşır. negatif değerler dosya işaretçisini dosya başlangıç doğru taşıyın.  
  
 `nFrom`  
 Gelen arama konumu. Olası değerler için Açıklamalar bölümüne bakın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem başarılı olursa dosya işaretçisini konumunu; Aksi takdirde, dönüş değeri tanımlanmamış gösteren bir işaretçi bir `CFileException` özel durumu oluşur.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin olası değerler aşağıdaki tabloda listelenmektedir `nFrom` parametresi.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|`CFile::begin`|Dosyanın başından arama.|  
|`CFile::current`|Dosya işaretçisini geçerli konumundan arama.|  
|`CFile::end`|Dosya sonundan arama.|  
  
 Bir dosya açıldığında dosya işaretçisini 0'da, dosyanın başlangıcına konumlandırıldı.  
  
 Dosya işaretçisini dosyanın sonunu aşan bir konuma ayarlayabilirsiniz. Bunu yaparsanız, dosyaya yazmak kadar dosyasının boyutunu artırmaz.  
  
 Özel durum işlendikten sonra bu yöntemi özel durum işleyicisi özel durum nesnesi silmeniz gerekir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#9](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_14.cpp)]  
  
##  <a name="seektobegin"></a>CFile::SeekToBegin  
 Dosya işaretçisini değerini dosyasının başlangıcına ayarlar.  
  
```  
void SeekToBegin();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `SeekToBegin()`eşdeğer olan `Seek( 0L, CFile::begin )`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]  
  
##  <a name="seektoend"></a>CFile::SeekToEnd  
 Dosya işaretçisini değerini mantıksal dosyanın sonuna ayarlar.  
  
```  
ULONGLONG SeekToEnd();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dosyanın bayt cinsinden uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 `SeekToEnd()`eşdeğer olan `CFile::Seek( 0L, CFile::end )`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#19](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_15.cpp)]  
  
##  <a name="setfilepath"></a>CFile::SetFilePath  
 Dosyasının yolunu belirtmek için bu işlevi çağırmak; Örneğin, bir dosyanın yolunu ne zaman kullanılabilir değilse, bir [CFile](../../mfc/reference/cfile-class.md) nesne yapılandırılmıştır, çağrı `SetFilePath` bunu sağlamak için.  
  
```  
virtual void SetFilePath(LPCTSTR lpszNewName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszNewName`  
 Yeni yolu belirten bir dize işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
> `SetFilePath`Dosya veya açmayın dosyası oluşturun; yalnızca ilişkilendirir `CFile` sonra kullanılabilir bir yol adına sahip nesne.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#20](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_16.cpp)]  
  
##  <a name="setlength"></a>CFile::SetLength  
 Dosya uzunluğunu değiştirmek için bu işlevini çağırın.  
  
```  
virtual void SetLength(ULONGLONG dwNewLen);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwNewLen`  
 İstenen dosyanın bayt cinsinden uzunluğu. Bu değer, geçerli dosya uzunluğu daha büyük veya küçük olabilir. Dosya genişletilmiş veya uygun şekilde kesildi.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  İle `CMemFile`, bu işlev throw bir `CMemoryException` nesnesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#11](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_17.cpp)]  
  
##  <a name="setstatus"></a>CFile::SetStatus  
 Bu dosya konumu ile ilişkili dosyanın durumunu ayarlar.  
  
```  
static void PASCAL SetStatus(
    LPCTSTR lpszFileName,  
    const CFileStatus& status,  
    CAtlTransactionManager* pTM = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFileName`  
 İstenen dosyanın yolu olan bir dize. Yolun göreli veya mutlak olabilir ve bir ağ adı içermelidir.  
  
 *durumu*  
 Yeni bir durum bilgisi içeren arabelleği. Çağrı **GetStatus** prefill için üye işlevini **CFileStatus** yapısı geçerli değerlerle sonra gerekli değişiklikleri yapın. Değer 0 ise, karşılık gelen durum öğesi güncelleştirilmez. Bkz: [GetStatus](#getstatus) üye işlevi bir açıklaması için **CFileStatus** yapısı.  
  
 `pTM`  
 CAtlTransactionManager nesnesine işaretçi  
  
### <a name="remarks"></a>Açıklamalar  
 Saati ayarlamak için değiştirme **m_mtime** alanını *durum*.  
  
 İçin bir arama yaparken lütfen unutmayın `SetStatus` yalnızca dosya özniteliklerini değiştirme girişimi ve **m_mtime** dosya durum yapısı üyesidir sıfır olmayan, öznitelikleri (zaman damgasını değiştirme de etkilenebilir yan etkiler özniteliklerinde olabilir). Yalnızca dosyanın özniteliklerini değiştirmek istiyorsanız, önce ayarlamanız **m_mtime** sıfır ve ardından bir çağrı yapmak için dosya durum yapısı üyesi `SetStatus`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#21](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_18.cpp)]  
  
##  <a name="unlockrange"></a>CFile::UnlockRange  
 Açık bir dosyayı bir bayt aralığı kilidini açar.  
  
```  
virtual void UnlockRange(
    ULONGLONG dwPos,  
    ULONGLONG dwCount);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwPos`  
 Kilidini açmak için bayt aralığı başlangıcı bayt uzaklığı.  
  
 `dwCount`  
 Kilidini açmak için aralıktaki bayt sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Açıklamasını görmek [LockRange](#lockrange) Ayrıntılar için üye işlevi.  
  
> [!NOTE]
>  Bu işlev için kullanılabilir değil `CMemFile`-türetilmiş sınıf.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#12](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_8.cpp)]  
  
##  <a name="write"></a>CFile::Write  
 Verileri bir arabelleğinden ilişkili dosyaya yazar `CFile` nesnesi.  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpBuf`  
 Dosyasına yazılacak olan verileri içeren kullanıcı tarafından sağlanan arabellek için bir işaretçi.  
  
 `nCount`  
 Arabellekteki aktarılacak bayt sayısı. Metin modunu dosyalar için satır başı satır besleme çiftleri tek karakter olarak sayılır.  
  
### <a name="remarks"></a>Açıklamalar  
 **Yazma** yanıt olarak disk dolu koşulu dahil olmak üzere çeşitli koşullar, bir özel durum oluşturur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#16](../../atl-mfc-shared/reference/codesnippet/cpp/cfile-class_19.cpp)]  
  
 Ayrıca, örnekler için bkz: [CFile::CFile](#cfile) ve [CFile::Open](#open).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek DRAWCLI](../../visual-cpp-samples.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CStdioFile sınıfı](../../mfc/reference/cstdiofile-class.md)   
 [CMemFile sınıfı](../../mfc/reference/cmemfile-class.md)
