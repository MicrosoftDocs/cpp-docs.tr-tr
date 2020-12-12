---
description: 'Daha fazla bilgi edinin: CFtpFileFind sınıfı'
title: CFtpFileFind sınıfı
ms.date: 05/28/2020
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
ms.openlocfilehash: 89d8a8232558c3afe9cf2f3a23d02226d8539aaf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184237"
---
# <a name="cftpfilefind-class"></a>CFtpFileFind sınıfı

FTP sunucularının Internet dosya aramalarında yardımlıklar.

## <a name="syntax"></a>Syntax

```
class CFtpFileFind : public CFileFind
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFtpFileFind:: Cftpfılefind](#cftpfilefind)|Bir `CFtpFileFind` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFtpFileFind:: FindFile](#findfile)|FTP sunucusundaki bir dosyayı bulur.|
|[CFtpFileFind:: FindNextFile](#findnextfile)|Önceki bir [FindFile](#findfile)çağrısından bir dosya aramaya devam eder.|
|[CFtpFileFind:: GetFileURL](#getfileurl)|Bulunan dosyanın yolu da dahil olmak üzere URL 'YI alır.|

## <a name="remarks"></a>Açıklamalar

`CFtpFileFind` arama işlemine başlayan üye işlevlerini içerir, bir dosya bulur ve URL 'YI ya da dosyayla ilgili diğer açıklayıcı bilgileri döndürür.

Internet ve yerel dosya için tasarlanan diğer MFC sınıfları, [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) ve [CFileFind](../../mfc/reference/cfilefind-class.md)' i içerir. İle birlikte `CFtpFileFind` , bu sınıflar, sunucu protokolüne veya dosya türüne (yerel bir makine ya da uzak bir sunucu) bakılmaksızın, istemcinin belirli dosyaları bulması için sorunsuz bir mekanizma sağlar. HTTP sunucularında arama yapmak için MFC sınıfı yoktur çünkü HTTP, aramalar için gerekli olan doğrudan dosya işlemesini desteklemez.

Ve diğer WinINet sınıflarının kullanımı hakkında daha fazla bilgi için `CFtpFileFind` bkz. [Wininet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

## <a name="example"></a>Örnek

Aşağıdaki kod, FTP sunucusunun geçerli dizinindeki tüm dosyaların nasıl numaralandırılacağını gösterir.

[!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CFtpFileFind`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

## <a name="cftpfilefindcftpfilefind"></a><a name="cftpfilefind"></a> CFtpFileFind:: Cftpfılefind

Bu üye işlevi bir nesne oluşturmak için çağırılır `CFtpFileFind` .

```
explicit CFtpFileFind(
    CFtpConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pConnection*<br/>
Bir `CFtpConnection` nesne işaretçisi. [CInternetSession:: GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)' i ÇAĞıRARAK bir FTP bağlantısı elde edebilirsiniz.

*dwContext*<br/>
Nesnenin bağlam tanımlayıcısı `CFtpFileFind` . Daha fazla bilgi **için aşağıdaki açıklamalara** bakın.

### <a name="remarks"></a>Açıklamalar

*DwContext* için varsayılan değer, MFC tarafından `CFtpFileFind` nesneyi oluşturan [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinden nesnesine gönderilir `CFtpFileFind` . Bağlam tanımlayıcıyı seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılabilirsiniz. Bağlam tanımlayıcısı, tanımlanan nesne üzerinde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) öğesine döndürülür. Bağlam tanımlayıcısı hakkında daha fazla bilgi için [Internet Ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

### <a name="example"></a>Örnek

  Bu konunun önceki kısımlarında bulunan sınıfa genel bakış bölümüne bakın.

## <a name="cftpfilefindfindfile"></a><a name="findfile"></a> CFtpFileFind:: FindFile

FTP dosyası bulmak için bu üye işlevini çağırın.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>Parametreler

*pstrName*<br/>
Bulunacak dosyanın adını içeren bir dize işaretçisi. NULL ise, çağrı joker karakter araması (*) olur.

*dwFlags*<br/>
Bu oturumun nasıl işleneceğini açıklayan bayraklar. Bu bayraklar bit düzeyinde OR işleci (&#124;) ile birleştirilebilir ve aşağıdaki gibidir:

- `INTERNET_FLAG_RELOAD`   Yerel olarak önbelleğe alınmış olsa bile, verileri iletişimden alın. Bu, varsayılan bayraktır.

- `INTERNET_FLAG_DONT_CACHE`   Verileri yerel olarak veya herhangi bir ağ geçidine göre önbelleğe mayın.

- `INTERNET_FLAG_RAW_DATA`   Ham verileri döndürmek için varsayılanı geçersiz kılın (FTP için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapıları).

- `INTERNET_FLAG_SECURE`   Güvenli Yuva Katmanı veya PCT ile iletişimdeki işlemlerin güvenliğini sağlar. Bu bayrak yalnızca HTTP istekleri için geçerlidir.

- `INTERNET_FLAG_EXISTING_CONNECT`   Mümkünse, `FindFile` her istek için yeni bir oturum oluşturmak yerine sunucuya mevcut bağlantıları yeni istekler için yeniden kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Genişletilmiş hata bilgilerini almak için, WIN32 [işlevini çağırın](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Açıklamalar

`FindFile`Ilk FTP dosyasını alma çağrısından sonra, sonrakı FTP dosyalarını almak Için [FindNextFile](#findnextfile) öğesini çağırabilirsiniz.

### <a name="example"></a>Örnek

  Bu konudaki önceki örneğe bakın.

## <a name="cftpfilefindfindnextfile"></a><a name="findnextfile"></a> CFtpFileFind:: FindNextFile

Bir dosya aramasının [FindFile](#findfile) üye işlevine çağrısıyla çalışmaya devam etmesi için bu üye işlevi çağırın.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Dönüş Değeri

Daha fazla dosya varsa sıfır dışı; Dosya, dizinde sonuncu ise veya bir hata oluştuysa sıfır olur. Genişletilmiş hata bilgilerini almak için, WIN32 [işlevini çağırın](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). Bulunan dosya dizindeki son dosya ise veya eşleşen dosya bulunamazsa, `GetLastError` işlev ERROR_NO_MORE_FILES döndürür.

### <a name="remarks"></a>Açıklamalar

Herhangi bir öznitelik işlevini çağırmadan önce bu işlevi en az bir kez çağırmanız gerekir (bkz. [CFileFind:: FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).

`FindNextFile` Win32 işlevi [FindNextFile dosyasını](/windows/win32/api/fileapi/nf-fileapi-findnextfilew)kaydırır.

### <a name="example"></a>Örnek

  Bu konunun önceki kısımlarında bulunan örneğe bakın.

## <a name="cftpfilefindgetfileurl"></a><a name="getfileurl"></a> CFtpFileFind:: GetFileURL

Belirtilen dosyanın URL 'sini almak için bu üye işlevini çağırın.

```
CString GetFileURL() const;
```

### <a name="return-value"></a>Dönüş Değeri

Evrensel Kaynak bulucunun (URL) dosyası ve yolu.

### <a name="remarks"></a>Açıklamalar

`GetFileURL` , sonucu URL biçiminde sunmasının dışında [CFileFind:: GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath) üye işlevine benzerdir. İle olduğu gibi `CFileFind::GetFilePath` , sonuç dosya adını içermez. Örneğin, `file1.txt` içinde bulunur `//moose/dir/file1.txt:` `ftp://moose/dir/` .

## <a name="see-also"></a>Ayrıca bkz.

[CFileFind sınıfı](../../mfc/reference/cfilefind-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind sınıfı](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile sınıfı](../../mfc/reference/chttpfile-class.md)
