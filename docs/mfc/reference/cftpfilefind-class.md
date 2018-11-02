---
title: CFtpFileFind sınıfı
ms.date: 11/04/2016
f1_keywords:
- CFtpFileFind
- AFXINET/CFtpFileFind
- AFXINET/CFtpFileFind::CFtpFileFind
- AFXINET/CFtpFileFind::FindFile
- AFXINET/CFtpFileFind::FindNextFile
- AFXINET/CFtpFileFind::GetFileURL
helpviewer_keywords:
- CFtpFileFind [MFC], CFtpFileFind
- CFtpFileFind [MFC], FindFile
- CFtpFileFind [MFC], FindNextFile
- CFtpFileFind [MFC], GetFileURL
ms.assetid: 9667cf01-657f-4b11-b9db-f11e5a7b4e4c
ms.openlocfilehash: 72d1eb147f8d7387a04f25cc008cc4d4638ba691
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548232"
---
# <a name="cftpfilefind-class"></a>CFtpFileFind sınıfı

İnternet'e yönelik dosyası aramalarındaki FTP sunucuları.

## <a name="syntax"></a>Sözdizimi

```
class CFtpFileFind : public CFileFind
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFtpFileFind::CFtpFileFind](#cftpfilefind)|Oluşturur bir `CFtpFileFind` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFtpFileFind::FindFile](#findfile)|FTP sunucusundaki bir dosya bulur.|
|[CFtpFileFind::FindNextFile](#findnextfile)|Bir önceki çağrıya bir dosya aramaya devam [FindFile](#findfile).|
|[CFtpFileFind::GetFileURL](#getfileurl)|Bulunan dosyasının yolunu da dahil olmak üzere URL'yi alır.|

## <a name="remarks"></a>Açıklamalar

`CFtpFileFind` bir arama başlatır, bir dosyayı bulun ve URL veya dosya hakkında tanımlayıcı diğer bilgilerini döndürmek üye işlevleri içerir.

Internet ve Aranan yerel dosya eklemek için tasarlanmış diğer MFC sınıfları [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) ve [CFileFind](../../mfc/reference/cfilefind-class.md). İle birlikte `CFtpFileFind`, bu sınıflar istemcinin protokolü veya dosya türü (yerel makine veya uzak bir sunucuya) sunucu bağımsız olarak, belirli dosyaları bulmak sorunsuz bir mekanizma sağlar. HTTP aramaları için gereken doğrudan dosya işleme desteklemediği için HTTP sunucularına arama için MFC sınıfı yok olduğuna dikkat edin.

Nasıl kullanılacağı hakkında daha fazla bilgi için `CFtpFileFind` ve diğer WinINet sınıfları başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md).

## <a name="example"></a>Örnek

Aşağıdaki kod, FTP sunucusunun geçerli dizindeki tüm dosyaları numaralandırma gösterilmiştir.

[!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CFtpFileFind`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

##  <a name="cftpfilefind"></a>  CFtpFileFind::CFtpFileFind

Bu üye işlevi oluşturmak için çağrılan bir `CFtpFileFind` nesne.

```
explicit CFtpFileFind(
    CFtpConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pConnection*<br/>
Bir işaretçi bir `CFtpConnection` nesne. FTP bağlantısı çağırarak elde edebileceğiniz [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection).

*dwContext*<br/>
İçerik tanımlayıcısı `CFtpFileFind` nesne. Bkz: **açıklamalar** Bu parametre hakkında daha fazla bilgi için.

### <a name="remarks"></a>Açıklamalar

İçin varsayılan değer *dwContext* MFC'ye tarafından gönderilen `CFtpFileFind` nesnesinden [Cınternetsession](../../mfc/reference/cinternetsession-class.md) oluşturulan nesne `CFtpFileFind` nesne. Bağlam tanımlayıcısını bir değere ayarlamak için bu varsayılanı geçersiz kılabilirsiniz. İçerik tanımlayıcısı döndürülür [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) durumu ile belirtilen nesneye sağlamak için. Makaleye göz atın [Internet ilk adımlar: WinINet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

### <a name="example"></a>Örnek

  Sınıfına genel bakış bu konunun önceki kısımlarındaki örneğe bakın.

##  <a name="findfile"></a>  CFtpFileFind::FindFile

Bir FTP dosyayı bulmak için bu üye işlevini çağırın.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>Parametreler

*pstrName*<br/>
Bulmak için dosya adını içeren bir dize işaretçisi. NULL ise, bir joker karakter araması (*) araması gerçekleştirir.

*CertOpenStore*<br/>
Bu oturumda nasıl ele alınacağını açıklayan bayrakları. Bu bayrak bit düzeyinde OR işleci ile birleştirilebilir (&#124;) ve aşağıdaki gibidir:

- INTERNET_FLAG_RELOAD veri alma hattan bile yerel olarak önbelleğe alınır. Varsayılan bayrağı budur.

- INTERNET_FLAG_DONT_CACHE önbelleğe almaz verileri yerel olarak veya herhangi bir ağ geçidi.

- INTERNET_FLAG_RAW_DATA ham verileri döndürmek için varsayılan geçersiz kılma ( [WIN32_FIND_DATA](/windows/desktop/api/minwinbase/ns-minwinbase-_win32_find_dataa) yapıları FTP için).

- Güvenli Yuva Katmanı veya yüzdesi kablo hareketleri INTERNET_FLAG_SECURE güvence altına alır Bu bayrağı yalnızca HTTP istekleri için geçerlidir.

- INTERNET_FLAG_EXISTING_CONNECT varsa mümkün tekrar sunucuya varolan bağlantılar yeni `FindFile` her istek için yeni bir oturum oluşturmak yerine istekleri.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Genişletilmiş hata bilgilerini almak için Win32 işlevini çağırmak [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).

### <a name="remarks"></a>Açıklamalar

Arama sonra `FindFile` ilk FTP dosyasını almak için çağırabilirsiniz ['larını](#findnextfile) sonraki FTP dosyaları almak için.

### <a name="example"></a>Örnek

  Bu konudaki önceki örneğe bakın.

##  <a name="findnextfile"></a>  CFtpFileFind::FindNextFile

Bu üye işlevi çağrısı ile başlamış bir dosya aramaya devam etmek için arama [FindFile](#findfile) üye işlevi.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Dönüş Değeri

Daha fazla dosya yoksa sıfır; sıfır. dosya bulundu sonuncu dizininde olması veya bir hata oluştu. Genişletilmiş hata bilgilerini almak için Win32 işlevini çağırmak [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360). Son dosya dizininde dosyası bulunamadı veya hiçbir eşleşen dosyaları bulunabilir, `GetLastError` ERROR_NO_MORE_FILES işlevi döndürür.

### <a name="remarks"></a>Açıklamalar

Herhangi bir öznitelik işlevi en az bir kez çağrılmadan önce bu işlevi çağırmanız gerekir (bkz [CFileFind::FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).

`FindNextFile` Win32 işlevini sarmalayan ['larını](/windows/desktop/api/fileapi/nf-fileapi-findnextfilea).

### <a name="example"></a>Örnek

  Bu konudaki örneğe bakın.

##  <a name="getfileurl"></a>  CFtpFileFind::GetFileURL

Belirtilen dosyanın URL'sini almak için bu üye işlevini çağırın.

```
CString GetFileURL() const;
```

### <a name="return-value"></a>Dönüş Değeri

Evrensel Kaynak Konum Belirleyicisi (URL), yol ve dosya.

### <a name="remarks"></a>Açıklamalar

`GetFileURL` üye işlevine benzer [CFileFind::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)formda URL'yi döndürür, dışında `ftp://moose/dir/file.txt`.

## <a name="see-also"></a>Ayrıca Bkz.

[CFileFind Sınıfı](../../mfc/reference/cfilefind-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind Sınıfı](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile Sınıfı](../../mfc/reference/chttpfile-class.md)
