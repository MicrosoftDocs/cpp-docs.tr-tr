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
ms.openlocfilehash: 2f4a394e29be135cac95edf6f504d8b066f53414
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866304"
---
# <a name="cftpfilefind-class"></a>CFtpFileFind sınıfı

FTP sunucularının Internet dosya aramalarında yardımlıklar.

## <a name="syntax"></a>Sözdizimi

```
class CFtpFileFind : public CFileFind
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFtpFileFind:: Cftpfılefind](#cftpfilefind)|`CFtpFileFind` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFtpFileFind:: FindFile](#findfile)|FTP sunucusundaki bir dosyayı bulur.|
|[CFtpFileFind:: FindNextFile](#findnextfile)|Önceki bir [FindFile](#findfile)çağrısından bir dosya aramaya devam eder.|
|[CFtpFileFind:: GetFileURL](#getfileurl)|Bulunan dosyanın yolu da dahil olmak üzere URL 'YI alır.|

## <a name="remarks"></a>Açıklamalar

`CFtpFileFind`, arama işlemine başlayan üye işlevlerini içerir, bir dosyayı bulur ve URL 'YI ya da dosyayla ilgili diğer açıklayıcı bilgileri döndürür.

Internet ve yerel dosya için tasarlanan diğer MFC sınıfları, [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) ve [CFileFind](../../mfc/reference/cfilefind-class.md)' i içerir. `CFtpFileFind`ile birlikte, bu sınıflar, sunucu protokolüne veya dosya türüne (yerel bir makine ya da uzak bir sunucu) bakılmaksızın, istemcinin belirli dosyaları bulması için sorunsuz bir mekanizma sağlar. HTTP sunucularında arama yapmak için MFC sınıfı olmadığını unutmayın; çünkü HTTP, aramalar için gerekli olan doğrudan dosya işlemesini desteklemez.

`CFtpFileFind` ve diğer WinINet sınıflarını kullanma hakkında daha fazla bilgi için bkz. [Wininet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

## <a name="example"></a>Örnek

Aşağıdaki kod, FTP sunucusunun geçerli dizinindeki tüm dosyaların nasıl numaralandırılacağını gösterir.

[!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFileFind](../../mfc/reference/cfilefind-class.md)

`CFtpFileFind`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

##  <a name="cftpfilefind"></a>CFtpFileFind:: Cftpfılefind

Bu üye işlevi bir `CFtpFileFind` nesnesi oluşturmak için çağırılır.

```
explicit CFtpFileFind(
    CFtpConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pConnection*<br/>
`CFtpConnection` nesnesine yönelik bir işaretçi. [CInternetSession:: GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)' i ÇAĞıRARAK bir FTP bağlantısı elde edebilirsiniz.

*dwContext*<br/>
`CFtpFileFind` nesnesi için bağlam tanımlayıcısı. Bu parametre hakkında daha fazla bilgi için bkz. **açıklamalar** .

### <a name="remarks"></a>Açıklamalar

*DwContext* için varsayılan değer, MFC tarafından `CFtpFileFind` nesnesini oluşturan [cınternetsession](../../mfc/reference/cinternetsession-class.md) nesnesinden `CFtpFileFind` nesnesine gönderilir. Bağlam tanımlayıcıyı seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılabilirsiniz. Bağlam tanımlayıcısı, tanımlanan nesne üzerinde durum sağlamak için [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) öğesine döndürülür. Bağlam tanımlayıcısı hakkında daha fazla bilgi için [Internet Ilk adımlar: WinINet](../../mfc/wininet-basics.md) makalesine bakın.

### <a name="example"></a>Örnek

  Bu konunun önceki kısımlarında bulunan sınıfa genel bakış bölümüne bakın.

##  <a name="findfile"></a>CFtpFileFind:: FindFile

FTP dosyası bulmak için bu üye işlevini çağırın.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>Parametreler

*pstrName*<br/>
Bulunacak dosyanın adını içeren bir dize işaretçisi. NULL ise, çağrı joker karakter araması yapar (*).

*dwFlags*<br/>
Bu oturumun nasıl işleneceğini açıklayan bayraklar. Bu bayraklar bit düzeyinde OR işleci (&#124;) ile birleştirilebilir ve aşağıdaki gibidir:

- INTERNET_FLAG_RELOAD, yerel olarak önbelleğe alınmış olsa bile, verileri iletişimden alın. Bu, varsayılan bayraktır.

- INTERNET_FLAG_DONT_CACHE, yerel olarak veya herhangi bir ağ geçitlerinde bulunan verileri önbelleğe almaz.

- INTERNET_FLAG_RAW_DATA, ham verileri döndürmek için varsayılanı geçersiz kılar (FTP için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapıları).

- INTERNET_FLAG_SECURE, Güvenli Yuva Katmanı veya PCT ile iletişimdeki işlemlerin güvenliğini sağlar. Bu bayrak yalnızca HTTP istekleri için geçerlidir.

- Mümkünse INTERNET_FLAG_EXISTING_CONNECT, her istek için yeni bir oturum oluşturmak yerine sunucuya mevcut bağlantıları yeni `FindFile` istekleri için yeniden kullanın.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Genişletilmiş hata bilgilerini almak için, WIN32 [işlevini çağırın](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror).

### <a name="remarks"></a>Açıklamalar

İlk FTP dosyasını almak için `FindFile` çağrıldıktan sonra, sonraki FTP dosyalarını almak için [FindNextFile](#findnextfile) öğesini çağırabilirsiniz.

### <a name="example"></a>Örnek

  Bu konudaki önceki örneğe bakın.

##  <a name="findnextfile"></a>CFtpFileFind:: FindNextFile

Bir dosya aramasının [FindFile](#findfile) üye işlevine çağrısıyla çalışmaya devam etmesi için bu üye işlevi çağırın.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Dönüş Değeri

Daha fazla dosya varsa sıfır dışı; Dosya, dizinde sonuncu ise veya bir hata oluştuysa sıfır olur. Genişletilmiş hata bilgilerini almak için, WIN32 [işlevini çağırın](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror). Bulunan dosya dizindeki son dosya ise veya eşleşen dosya bulunamazsa, `GetLastError` işlevi ERROR_NO_MORE_FILES döndürür.

### <a name="remarks"></a>Açıklamalar

Herhangi bir öznitelik işlevini çağırmadan önce bu işlevi en az bir kez çağırmanız gerekir (bkz. [CFileFind:: FindNextFile](../../mfc/reference/cfilefind-class.md#findnextfile)).

`FindNextFile`, [FindNextFile](/windows/win32/api/fileapi/nf-fileapi-findnextfilew)Win32 işlevini kaydırır.

### <a name="example"></a>Örnek

  Bu konunun önceki kısımlarında bulunan örneğe bakın.

##  <a name="getfileurl"></a>CFtpFileFind:: GetFileURL

Belirtilen dosyanın URL 'sini almak için bu üye işlevini çağırın.

```
CString GetFileURL() const;
```

### <a name="return-value"></a>Dönüş Değeri

Evrensel Kaynak bulucunun (URL) dosyası ve yolu.

### <a name="remarks"></a>Açıklamalar

`GetFileURL`, [CFileFind:: GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)üye işlevine benzer, ancak URL 'yi `ftp://moose/dir/file.txt`olarak döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CFileFind Sınıfı](../../mfc/reference/cfilefind-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind Sınıfı](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[CHttpFile Sınıfı](../../mfc/reference/chttpfile-class.md)
