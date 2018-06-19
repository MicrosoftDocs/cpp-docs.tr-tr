---
title: CFileFind sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFileFind
- AFX/CFileFind
- AFX/CFileFind::CFileFind
- AFX/CFileFind::Close
- AFX/CFileFind::FindFile
- AFX/CFileFind::FindNextFile
- AFX/CFileFind::GetCreationTime
- AFX/CFileFind::GetFileName
- AFX/CFileFind::GetFilePath
- AFX/CFileFind::GetFileTitle
- AFX/CFileFind::GetFileURL
- AFX/CFileFind::GetLastAccessTime
- AFX/CFileFind::GetLastWriteTime
- AFX/CFileFind::GetLength
- AFX/CFileFind::GetRoot
- AFX/CFileFind::IsArchived
- AFX/CFileFind::IsCompressed
- AFX/CFileFind::IsDirectory
- AFX/CFileFind::IsDots
- AFX/CFileFind::IsHidden
- AFX/CFileFind::IsNormal
- AFX/CFileFind::IsReadOnly
- AFX/CFileFind::IsSystem
- AFX/CFileFind::IsTemporary
- AFX/CFileFind::MatchesMask
- AFX/CFileFind::CloseContext
- AFX/CFileFind::m_pTM
dev_langs:
- C++
helpviewer_keywords:
- CFileFind [MFC], CFileFind
- CFileFind [MFC], Close
- CFileFind [MFC], FindFile
- CFileFind [MFC], FindNextFile
- CFileFind [MFC], GetCreationTime
- CFileFind [MFC], GetFileName
- CFileFind [MFC], GetFilePath
- CFileFind [MFC], GetFileTitle
- CFileFind [MFC], GetFileURL
- CFileFind [MFC], GetLastAccessTime
- CFileFind [MFC], GetLastWriteTime
- CFileFind [MFC], GetLength
- CFileFind [MFC], GetRoot
- CFileFind [MFC], IsArchived
- CFileFind [MFC], IsCompressed
- CFileFind [MFC], IsDirectory
- CFileFind [MFC], IsDots
- CFileFind [MFC], IsHidden
- CFileFind [MFC], IsNormal
- CFileFind [MFC], IsReadOnly
- CFileFind [MFC], IsSystem
- CFileFind [MFC], IsTemporary
- CFileFind [MFC], MatchesMask
- CFileFind [MFC], CloseContext
- CFileFind [MFC], m_pTM
ms.assetid: 9990068c-b023-4114-9580-a50182d15240
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf77a5581dd9e8c9181c61287b6032f700d7d64b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376577"
---
# <a name="cfilefind-class"></a>CFileFind sınıfı
Yerel dosya aramaları gerçekleştirir ve temel sınıfı olan [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) ve [CFtpFileFind](../../mfc/reference/cftpfilefind-class.md), Internet dosya aramaları gerçekleştirin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CFileFind : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileFind::CFileFind](#cfilefind)|Oluşturan bir `CFileFind` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileFind::Close](#close)|Arama isteği kapatır.|  
|[CFileFind::FindFile](#findfile)|Belirtilen dosya adı için bir dizin arar.|  
|[CFileFind::FindNextFile](#findnextfile)|Dosya arama önceki çağrısından devam [FindFile](#findfile).|  
|[CFileFind::GetCreationTime](#getcreationtime)|Dosyanın oluşturulduğu saati alır.|  
|[CFileFind::GetFileName](#getfilename)|Bulunan dosya uzantısı dahil adını alır|  
|[CFileFind::GetFilePath](#getfilepath)|Bulunan dosyanın tam yolunu alır.|  
|[CFileFind::GetFileTitle](#getfiletitle)|Bulunan dosya başlığını alır. Başlık uzantısı içermez.|  
|[CFileFind::GetFileURL](#getfileurl)|Bulunan dosyasının dosya yolunda dahil olmak üzere URL'yi alır.|  
|[CFileFind::GetLastAccessTime](#getlastaccesstime)|Dosyaya son erişilen zaman alır.|  
|[CFileFind::GetLastWriteTime](#getlastwritetime)|Dosyanın en son değiştirilen ve kaydedilen zaman alır.|  
|[CFileFind::GetLength](#getlength)|Bulunan dosyanın bayt cinsinden uzunluğunu alır.|  
|[CFileFind::GetRoot](#getroot)|Kök dizininde bulunan dosyayı alır.|  
|[CFileFind::IsArchived](#isarchived)|Bulunan dosya arşivlendi varsa belirler.|  
|[CFileFind::IsCompressed](#iscompressed)|Bulunan dosyayı sıkıştırılmış olup olmadığını belirler.|  
|[CFileFind::IsDirectory](#isdirectory)|Bulunan dosyanın bir dizin olup olmadığını belirler.|  
|[CFileFind::IsDots](#isdots)|Bulunan dosyanın adını adı olup olmadığını belirler "."veya"..", aslında bir dizin belirten.|  
|[CFileFind::IsHidden](#ishidden)|Bulunan dosyanın gizli olduğunu belirler.|  
|[CFileFind::IsNormal](#isnormal)|Bulunan dosyanın normal olup olmadığını belirler (diğer bir deyişle, diğer öznitelikleri yok).|  
|[CFileFind::IsReadOnly](#isreadonly)|Bulunan dosyanın salt okunur olup olmadığını belirler.|  
|[CFileFind::IsSystem](#issystem)|Bulunan dosyanın bir sistem dosyası olup olmadığını belirler.|  
|[CFileFind::IsTemporary](#istemporary)|Bulunan dosyanın geçici olup olmadığını belirler.|  
|[CFileFind::MatchesMask](#matchesmask)|İstenen dosya öznitelikleri bulunacak gösterir.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileFind::CloseContext](#closecontext)|Geçerli arama tanıtıcı tarafından belirtilen dosya kapatır.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CFileFind::m_pTM](#m_ptm)|İşaretçi bir `CAtlTransactionManager` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CFileFind` bir arama başlatır, bir dosyayı bulmak ve iade başlık, adı veya dosyasının yolunu üye işlevlerini içerir. Internet aramalarda üye fonksiyonu [GetFileURL](#getfileurl) dosyanın URL'sini döndürür.  
  
 `CFileFind` diğer iki MFC sınıfları için temel sınıfı belirli bir sunucu türlerini aramak için tasarlanmıştır: `CGopherFileFind` özellikle gopher sunucularıyla çalışır ve `CFtpFileFind` özellikle FTP sunucularıyla çalışır. Birlikte, bu üç sınıfları istemcinin dosyaları, sunucu protokolü, dosya türü veya konumu, bağımsız olarak yerel makine ya da uzak bir sunucuya bulmak sorunsuz bir mekanizma sağlar.  
  
 Aşağıdaki kodu her dosyanın adını yazdırma geçerli dizindeki tüm dosyaları numaralandırma:  
  
 [!code-cpp[NVC_MFCFiles#31](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_1.cpp)]  
  
 Bu kod örneği basit tutmak için C++ Standart kitaplığı kullanır `cout` sınıfı. `cout` Satır yerini çağrısıyla `CListBox::AddString`, örneğin, bir grafik kullanıcı arabirimi ile bir programda.  
  
 Nasıl kullanılacağı hakkında daha fazla bilgi için `CFileFind` ve diğer WinINet sınıfları başlıklı makaleye bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CFileFind`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="cfilefind"></a>  CFileFind::CFileFind  
 Bu üye işlevi aldığında çağrılan bir `CFileFind` nesnesi oluşturulur.  
  
```  
CFileFind();  
CFileFind(CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Parametreler  
 `pTM`  
 CAtlTransactionManager nesnesine işaretçi  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetFileName](#getfilename).  
  
##  <a name="close"></a>  CFileFind::Close  
 Aramayı sonlandırmak, bağlam Sıfırla ve tüm kaynakları serbest bırakmak için bu üye işlevini çağırın.  
  
```  
void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra **Kapat**, yeni bir gerekmez `CFileFind` örneği çağırmadan önce [FindFile](#findfile) yeni bir arama başlatmak için.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetFileName](#getfilename).  
  
##  <a name="closecontext"></a>  CFileFind::CloseContext  
 Geçerli arama tanıtıcı tarafından belirtilen dosya kapatır.  
  
```  
virtual void CloseContext();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Arama tanıtıcısı geçerli değeri tarafından belirtilen dosya kapatır. Bu işlev varsayılan davranışı değiştirmek için geçersiz kılar.  
  
 Çağırmalısınız [FindFile](#findfile) veya ['larını](#findnextfile) geçerli arama tanıtıcısı almak için en az bir kez işlevleri. **FindFile** ve `FindNextFile` işlevleri bir verilen adıyla eşleşen adlara sahip dosyaları bulmak için arama tanıtıcısı kullanın.  
  
##  <a name="findfile"></a>  CFileFind::FindFile  
 Bir dosya aramayı açmak için bu üye işlevini çağırın.  
  
```  
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,  
    DWORD dwUnused = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `pstrName`  
 Bulunacak dosyasının adı içeren bir dize için bir işaretçi. Geçirirseniz **NULL** için `pstrName`, **FindFile** bir joker karakter mu (*.\*) arama.  
  
 *dwUnused*  
 Yapmak için ayrılmış **FindFile** türetilen sınıflar ile çok biçimli. 0 olmalıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Genişletilmiş hata bilgilerini için Win32 işlevini çağırın [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra **FindFile** dosya aramaya başlamak için çağrı ['larını](#findnextfile) sonraki dosyaları alınamadı. Çağırmalısınız `FindNextFile` aşağıdaki öznitelik hiçbirini üye işlevleri çağırmadan önce en az bir kez:  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="findnextfile"></a>  CFileFind::FindNextFile  
 Önceki çağrısından dosya aramaya devam etmek için bu üye işlevini çağırın [FindFile](#findfile).  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha fazla dosya varsa sıfır olmayan; sıfır bulunan dosya sonuncu dizininde olması veya bir hata oluştu. Genişletilmiş hata bilgilerini için Win32 işlevini çağırın [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360). Son dosya dizininde bulunan dosya ise veya eşleşme varsa dosyaları bulunabilir, `GetLastError` işlevi ERROR_NO_MORE_FILES döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız `FindNextFile` aşağıdaki öznitelik hiçbirini üye işlevleri çağırmadan önce en az bir kez:  
  
- [GetCreationTime](#getcreationtime)  
  
- [GetFileName](#getfilename)  
  
- [GetFileTitle](#getfiletitle)  
  
- [GetFilePath](#getfilepath)  
  
- [GetFileURL](#getfileurl)  
  
- [GetLastAccessTime](#getlastaccesstime)  
  
- [GetLastWriteTime](#getlastwritetime)  
  
- [GetLength](#getlength)  
  
- [GetRoot](#getroot)  
  
- [IsArchived](#isarchived)  
  
- [IsCompressed](#iscompressed)  
  
- [IsDirectory](#isdirectory)  
  
- [IsDots](#isdots)  
  
- [IsHidden](#ishidden)  
  
- [IsNormal](#isnormal)  
  
- [IsReadOnly](#isreadonly)  
  
- [IsSystem](#issystem)  
  
- [IsTemporary](#istemporary)  
  
- [MatchesMask](#matchesmask)  
  
 `FindNextFile` Win32 işlevi sarmalar ['larını](http://msdn.microsoft.com/library/windows/desktop/aa364428).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="getcreationtime"></a>  CFileFind::GetCreationTime  
 Belirtilen dosyanın oluşturulduğu zaman almak için bu üye işlevini çağırın.  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pTimeStamp`  
 Bir işaretçi bir [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) dosyanın oluşturulduğu zaman içeren yapısı.  
  
 `refTime`  
 Bir başvuru bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; işlem başarısız olursa 0. `GetCreationTime` yalnızca 0 döndürür ['larını](#findnextfile) bu bilgisayarda hiç çağrıldı `CFileFind` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetCreationTime`.  
  
> [!NOTE]
>  Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgası uygulamak için aynı semantiğini kullanır. Bu işlev temel alınan dosya sistemi veya sunucunun saat özniteliği tutma desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değeri döndürebilir. Bkz: [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı saat biçimleri hakkında bilgi için. Bazı işlemi sistemlerinde döndürülen bölge yerel makineye olan dosyasının bulunduğu süresi içinde'dır. Win32 bkz [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) daha fazla bilgi için API.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetLength](#getlength).  
  
##  <a name="getfilename"></a>  CFileFind::GetFileName  
 Bulunan dosyanın adını almak için bu üye işlevini çağırın.  
  
```  
virtual CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 En son bulunan dosya adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) GetFileName çağırmadan önce en az bir kez.  
  
 `GetFileName` üç biri `CFileFind` bazı dönüş dosya adının üye işlevleri. Aşağıdaki listede, üç ve bunların nasıl değişiklik açıklanmaktadır:  
  
- `GetFileName` Dosya adı uzantısı dahil, döndürür. Örneğin, arama `GetFileName` dosyasını ilgili kullanıcı iletisi oluşturmak için `c:\myhtml\myfile.txt` dosya adı döndürür `myfile.txt`.  
  
- [GetFilePath](#getfilepath) dosyasının tam yolu döndürür. Örneğin, arama `GetFilePath` dosyasını ilgili kullanıcı iletisi oluşturmak için `c:\myhtml\myfile.txt` dosya yolunu döndürür `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) dosya uzantısı hariç dosya adını döndürür. Örneğin, arama `GetFileTitle` dosyasını ilgili kullanıcı iletisi oluşturmak için `c:\myhtml\myfile.txt` dosya başlığı döndürür `myfile`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#32](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_2.cpp)]  
  
##  <a name="getfilepath"></a>  CFileFind::GetFilePath  
 Belirtilen dosyanın tam yolunu almak için bu üye işlevini çağırın.  
  
```  
virtual CString GetFilePath() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dosya yolu.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetFilePath`.  
  
 `GetFilePath` üç biri `CFileFind` bazı dönüş dosya adının üye işlevleri. Aşağıdaki listede, üç ve bunların nasıl değişiklik açıklanmaktadır:  
  
- [GetFileName](#getfilename) uzantısı dahil dosya adını döndürür. Örneğin, arama `GetFileName` dosyasını ilgili kullanıcı iletisi oluşturmak için `c:\myhtml\myfile.txt` dosya adı döndürür `myfile.txt`.  
  
- `GetFilePath` dosyanın tüm yolunu döndürür. Örneğin, arama `GetFilePath` dosyasını ilgili kullanıcı iletisi oluşturmak için `c:\myhtml\myfile.txt` dosya yolunu döndürür `c:\myhtml\myfile.txt`.  
  
- [GetFileTitle](#getfiletitle) dosya uzantısı hariç dosya adını döndürür. Örneğin, arama `GetFileTitle` dosyasını ilgili kullanıcı iletisi oluşturmak için `c:\myhtml\myfile.txt` dosya başlığı döndürür `myfile`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getfiletitle"></a>  CFileFind::GetFileTitle  
 Bulunan dosya başlığı almak için bu üye işlevini çağırın.  
  
```  
virtual CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dosya başlığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetFileTitle`.  
  
 `GetFileTitle` üç biri `CFileFind` bazı dönüş dosya adının üye işlevleri. Aşağıdaki listede, üç ve bunların nasıl değişiklik açıklanmaktadır:  
  
- [GetFileName](#getfilename) uzantısı dahil dosya adını döndürür. Örneğin, arama `GetFileName` dosyasını ilgili kullanıcı iletisi oluşturmak için `c:\myhtml\myfile.txt` dosya adı döndürür `myfile.txt`.  
  
- [GetFilePath](#getfilepath) dosyasının tam yolu döndürür. Örneğin, arama `GetFilePath` dosyasını ilgili kullanıcı iletisi oluşturmak için `c:\myhtml\myfile.txt` dosya yolunu döndürür `c:\myhtml\myfile.txt`.  
  
- `GetFileTitle` Dosya uzantısı hariç dosya adını döndürür. Örneğin, arama `GetFileTitle` dosyasını ilgili kullanıcı iletisi oluşturmak için `c:\myhtml\myfile.txt` dosya başlığı döndürür `myfile`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getfileurl"></a>  CFileFind::GetFileURL  
 Belirtilen URL almak için bu üye işlevini çağırın.  
  
```  
virtual CString GetFileURL() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tam URL.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetFileURL`.  
  
 `GetFileURL` üye işlevine benzer [GetFilePath](#getfilepath), URL biçiminde döndürür dışında `file://path`. Örneğin, arama `GetFileURL` tam URL'sini almak için `myfile.txt` URL'yi döndürür `file://c:\myhtml\myfile.txt`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetFileName](#getfilename).  
  
##  <a name="getlastaccesstime"></a>  CFileFind::GetLastAccessTime  
 Belirtilen dosya son erişilme zamanı almak için bu üye işlevini çağırın.  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `refTime`  
 Bir başvuru bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesi.  
  
 `pTimeStamp`  
 Bir işaretçi bir [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) dosyaya son erişim saati içeren yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; işlem başarısız olursa 0. `GetLastAccessTime` yalnızca 0 döndürür ['larını](#findnextfile) bu bilgisayarda hiç çağrıldı `CFileFind` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetLastAccessTime`.  
  
> [!NOTE]
>  Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgası uygulamak için aynı semantiğini kullanır. Bu işlev temel alınan dosya sistemi veya sunucunun saat özniteliği tutma desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değeri döndürebilir. Bkz: [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı saat biçimleri hakkında bilgi için. Bazı işlemi sistemlerinde döndürülen bölge yerel makineye olan dosyasının bulunduğu süresi içinde'dır. Win32 bkz [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) daha fazla bilgi için API.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetLength](#getlength).  
  
##  <a name="getlastwritetime"></a>  CFileFind::GetLastWriteTime  
 Dosya değiştirildi en son ne zaman almak için bu üye işlevini çağırın.  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pTimeStamp`  
 Bir işaretçi bir [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) dosya için en son yazıldı saati içeren yapısı.  
  
 `refTime`  
 Bir başvuru bir [CTime](../../atl-mfc-shared/reference/ctime-class.md) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; işlem başarısız olursa 0. `GetLastWriteTime` yalnızca 0 döndürür ['larını](#findnextfile) bu bilgisayarda hiç çağrıldı `CFileFind` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetLastWriteTime`.  
  
> [!NOTE]
>  Tüm dosya sistemleri, bu işlev tarafından döndürülen zaman damgası uygulamak için aynı semantiğini kullanır. Bu işlev temel alınan dosya sistemi veya sunucunun saat özniteliği tutma desteklemiyorsa, diğer zaman damgası işlevleri tarafından döndürülen aynı değeri döndürebilir. Bkz: [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı saat biçimleri hakkında bilgi için. Bazı işlemi sistemlerinde döndürülen bölge yerel makineye olan dosyasının bulunduğu süresi içinde'dır. Win32 bkz [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) daha fazla bilgi için API.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetLength](#getlength).  
  
##  <a name="getlength"></a>  CFileFind::GetLength  
 Bulunan dosyanın bayt cinsinden uzunluğu almak için bu üye işlevini çağırın.  
  
```  
ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bulunan dosyanın bayt cinsinden uzunluğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetLength`.  
  
 `GetLength` Win32 yapısı kullanır [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) almak ve bayt olarak dosya boyutu değerini döndürür.  
  
> [!NOTE]
>  MFC 7.0 itibariyle `GetLength` 64-bit tamsayı türlerini destekler. Daha önce bu kitaplığı daha yeni sürümü ile oluşturulmuş var olan kodu kesilmesi uyarılarla neden olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#33](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_3.cpp)]  
  
##  <a name="getroot"></a>  CFileFind::GetRoot  
 Kök dizininde bulunan dosya almak için bu üye işlevini çağırın.  
  
```  
virtual CString GetRoot() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etkin arama kökü.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `GetRoot`.  
  
 Bu üye işlevi bir aramayı başlatmak için kullanılan yolu adı ve sürücü belirleyici döndürür. Örneğin, arama [FindFile](#findfile) ile `*.dat` sonuçlanır `GetRoot` boş bir dize döndürüyor. Bir yol gibi geçirme `c:\windows\system\*.dll`, **FindFile** sonuçları `GetRoot` döndüren `c:\windows\system\`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetFileName](#getfilename).  
  
##  <a name="isarchived"></a>  CFileFind::IsArchived  
 Bulunan dosya arşivlendi varsa belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsArchived() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamaların yedeklenmesini veya kaldırılan FILE_ATTRIBUTE_ARCHIVE, tanımlanan dosya özniteliği ile bir arşiv dosyasına işaretlemek [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı.  
  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsArchived`.  
  
 Üye işlevine bakın [MatchesMask](#matchesmask) dosya öznitelikleri tam bir listesi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetLength](#getlength).  
  
##  <a name="iscompressed"></a>  CFileFind::IsCompressed  
 Bulunan dosyayı sıkıştırılmış olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsCompressed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Sıkıştırılmış bir dosya FILE_ATTRIBUTE_COMPRESSED ile işaretlendiğinden, dosya özniteliği tanımlanan [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı. Bir dosya için bu öznitelik, sıkıştırılmış dosyasındaki verilerin tümü gösterir. Bir dizin için bu öznitelik, sıkıştırma yeni oluşturulan dosya ve alt dizinler için varsayılan değer gösterir.  
  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsCompressed`.  
  
 Üye işlevine bakın [MatchesMask](#matchesmask) dosya öznitelikleri tam bir listesi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetLength](#getlength).  
  
##  <a name="isdirectory"></a>  CFileFind::IsDirectory  
 Bulunan dosyanın bir dizin olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsDirectory() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizini olan bir dosyayı dosya özniteliği tanımlanan FILE_ATTRIBUTE_DIRECTORY işaretlenmiş [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı.  
  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsDirectory`.  
  
 Üye işlevine bakın [MatchesMask](#matchesmask) dosya öznitelikleri tam bir listesi.  
  
### <a name="example"></a>Örnek  
 Bu küçük bir program C:\ sürücüsündeki her dizini recurses ve dizin adı yazdırır.  
  
 [!code-cpp[NVC_MFCFiles#34](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_4.cpp)]  
  
##  <a name="isdots"></a>  CFileFind::IsDots  
 Dosyalar ile yineleme sırasında için geçerli dizin ve üst dizin işaretçileri test etmek için bu üye işlevini çağırın.  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bulunan dosyanın adı varsa, sıfır olmayan "."veya"..", bulunan dosyanın gerçekten bir dizin olduğunu gösterir. Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsDots`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::IsDirectory](#isdirectory).  
  
##  <a name="ishidden"></a>  CFileFind::IsHidden  
 Bulunan dosyanın gizli olduğunu belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya özniteliği ile FILE_ATTRIBUTE_HIDDEN işaretlenir, gizli dosya tanımlanan içinde [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı. Gizli bir dosya bir sıradan dizin listesinde yer almaz.  
  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsHidden`.  
  
 Üye işlevine bakın [MatchesMask](#matchesmask) dosya öznitelikleri tam bir listesi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetLength](#getlength).  
  
##  <a name="isnormal"></a>  CFileFind::IsNormal  
 Bulunan dosyanın normal bir dosya olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsNormal() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya özniteliği FILE_ATTRIBUTE_NORMAL ile işaretlenmiş dosyaları tanımlanan içinde [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı. Normal bir dosya Ayarla özniteliğe sahip değildir. Diğer tüm dosya öznitelikleri bu özniteliği geçersiz kılar.  
  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsNormal`.  
  
 Üye işlevine bakın [MatchesMask](#matchesmask) dosya öznitelikleri tam bir listesi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetLength](#getlength).  
  
##  <a name="isreadonly"></a>  CFileFind::IsReadOnly  
 Bulunan dosyanın salt okunur olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsReadOnly() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Salt okunur bir dosya FILE_ATTRIBUTE_READONLY ile işaretlendiğinden, dosya özniteliği tanımlanan [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı. Uygulamalar bu tür bir dosyayı okuyabilir, ancak yazma veya silin.  
  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsReadOnly`.  
  
 Üye işlevine bakın [MatchesMask](#matchesmask) dosya öznitelikleri tam bir listesi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetLength](#getlength).  
  
##  <a name="issystem"></a>  CFileFind::IsSystem  
 Bulunan dosya bir sistem dosyası olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsSystem() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir sistem dosyası FILE_ATTRIBUTE_SYSTEM ile işaretlendiğinden, dosya özniteliği tanımlanan [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı. Bir sistem dosyasının parçası olan veya yalnızca işletim sistemi tarafından kullanılır.  
  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsSystem`.  
  
 Üye işlevine bakın [MatchesMask](#matchesmask) dosya öznitelikleri tam bir listesi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetLength](#getlength).  
  
##  <a name="istemporary"></a>  CFileFind::IsTemporary  
 Bulunan dosyanın geçici bir dosya olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsTemporary() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçici bir dosya FILE_ATTRIBUTE_TEMPORARY ile işaretlendiğinden, dosya özniteliği tanımlanan [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) yapısı. Geçici bir dosya geçici depolama için kullanılır. Uygulamalar, yalnızca kesinlikle gerekli olduğunda veya dosyaya yazmak. Dosyanın verilerin çoğu dosya hemen silinecek medyaya temizlendi nedeni olmadan bellekte kalır.  
  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `IsTemporary`.  
  
 Üye işlevine bakın [MatchesMask](#matchesmask) dosya öznitelikleri tam bir listesi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CFileFind::GetLength](#getlength).  
  
##  <a name="m_ptm"></a>  CFileFind::m_pTM  
 İşaretçi bir `CAtlTransactionManager` nesnesi.  
  
```  
CAtlTransactionManager* m_pTM;  
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="matchesmask"></a>  CFileFind::MatchesMask  
 Dosya öznitelikleri bulunan dosyada test etmek için bu üye işlevini çağırın.  
  
```  
virtual BOOL MatchesMask(DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `dwMask`  
 Tanımlanan bir veya daha fazla dosya özniteliklerini belirtir [WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740) bulunan dosya yapısı. Birden çok öznitelik aramak için Bitsel veya kullanın (&#124;) işleci. Aşağıdaki öznitelikler herhangi bir bileşimini kabul edilebilir:  
  
-   FILE_ATTRIBUTE_ARCHIVE dosyayı bir arşiv dosyasıdır. Uygulamalar bu öznitelik yedekleme veya kaldırma için dosyaları için kullanın.  
  
-   Dosya veya dizin FILE_ATTRIBUTE_COMPRESSED sıkıştırılır. Bir dosya için bu sıkıştırılmış dosyasındaki verilerin tümü anlamına gelir. Bir dizin için bu sıkıştırma yeni oluşturulan dosya ve alt dizinler için varsayılan değer anlamına gelir.  
  
-   FILE_ATTRIBUTE_DIRECTORY dosyayı bir dizindir.  
  
-   FILE_ATTRIBUTE_NORMAL dosya Ayarla özniteliğe sahip değildir. Bu öznitelik, yalnızca tek başına kullanıldığında geçerlidir. Diğer tüm dosya öznitelikleri bu özniteliği geçersiz kılar.  
  
-   Dosya gizli FILE_ATTRIBUTE_HIDDEN. Bu bir sıradan dizin listesinde değil eklenir.  
  
-   FILE_ATTRIBUTE_READONLY dosya salt okunur. Uygulamaların dosyayı okuma ancak olamaz yazma veya silin.  
  
-   Dosya parçası olan veya yalnızca işletim sistemi tarafından kullanılan FILE_ATTRIBUTE_SYSTEM.  
  
-   Dosya geçici depolama için kullanılan FILE_ATTRIBUTE_TEMPORARY. Uygulamalar, yalnızca kesinlikle gerekli olduğunda veya dosyaya yazmak. Dosyanın verilerin çoğu dosya hemen silinecek medyaya temizlendi nedeni olmadan bellekte kalır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Genişletilmiş hata bilgilerini için Win32 işlevini çağırın [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız ['larını](#findnextfile) çağırmadan önce en az bir kez `MatchesMask`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCFiles#35](../../atl-mfc-shared/reference/codesnippet/cpp/cfilefind-class_5.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind sınıfı](../../mfc/reference/cftpfilefind-class.md)   
 [CGopherFileFind sınıfı](../../mfc/reference/cgopherfilefind-class.md)   
 [CInternetFile sınıfı](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile sınıfı](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile Sınıfı](../../mfc/reference/chttpfile-class.md)
