---
title: CFtpFileFind Sınıf
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
ms.openlocfilehash: cf4afb4a683c2d0cf5f2977107d02ee300a53cb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373748"
---
# <a name="cftpfilefind-class"></a>CFtpFileFind Sınıf

FTP sunucularının Internet dosya aramalarında yardımlar.

## <a name="syntax"></a>Sözdizimi

```
class CFtpFileFind : public CFileFind
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFtpFileFind::CFtpFileBul](#cftpfilefind)|Bir `CFtpFileFind` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFtpFileFind::Dosya bul](#findfile)|FTP sunucusunda bir dosya bulur.|
|[CFtpFileFind::FindNextFile](#findnextfile)|[FindFile](#findfile)için önceki bir aramadan bir dosya aramasına devam ediyor.|
|[CFtpFileFind::GetFileURL](#getfileurl)|Bulunan dosyanın yolu da dahil olmak üzere URL'yi alır.|

## <a name="remarks"></a>Açıklamalar

`CFtpFileFind`aramayı başlatan, dosyayı bulup URL'yi veya dosya yla ilgili diğer açıklayıcı bilgileri döndüren üye işlevleri içerir.

Internet ve yerel dosya aranan için tasarlanmış diğer MFC sınıfları [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md) ve [CFileFind](../../mfc/reference/cfilefind-class.md)içerir. Bu `CFtpFileFind`sınıflar, sunucu protokolü veya dosya türünden (yerel bir makine veya uzak sunucu) bağımsız olarak, istemcinin belirli dosyaları bulması için sorunsuz bir mekanizma sağlar. HTTP aramalar için gerekli doğrudan dosya işleme desteklemez, çünkü HTTP sunucularında arama için hiçbir MFC sınıfı olduğunu unutmayın.

Nasıl kullanılacağı `CFtpFileFind` ve diğer WinInet sınıfları hakkında daha fazla bilgi için, [WinInet ile](../../mfc/win32-internet-extensions-wininet.md)makale Internet Programlama bakın.

## <a name="example"></a>Örnek

Aşağıdaki kod, FTP sunucusunun geçerli dizinindeki tüm dosyaların nasıl sayısala gösteriş yapılacağını gösterir.

[!code-cpp[NVC_MFCWinInet#8](../../mfc/codesnippet/cpp/cftpfilefind-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfilefind](../../mfc/reference/cfilefind-class.md)

`CFtpFileFind`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="cftpfilefindcftpfilefind"></a><a name="cftpfilefind"></a>CFtpFileFind::CFtpFileBul

Bu üye işlev bir `CFtpFileFind` nesne oluşturmak için çağrılır.

```
explicit CFtpFileFind(
    CFtpConnection* pConnection,
    DWORD_PTR dwContext = 1);
```

### <a name="parameters"></a>Parametreler

*pBağlantı*<br/>
Bir `CFtpConnection` nesneye işaretçi. [CInternetSession::GetFtpConnection'ı](../../mfc/reference/cinternetsession-class.md#getftpconnection)arayarak FTP bağlantısı elde edebilirsiniz.

*dwBağlam*<br/>
Nesneiçin bağlam tanımlayıcısı. `CFtpFileFind` Bu parametre hakkında daha fazla bilgi için **Açıklamalar'a** bakın.

### <a name="remarks"></a>Açıklamalar

*dwContext* için varsayılan değer, MFC `CFtpFileFind` tarafından `CFtpFileFind` nesneyi oluşturan [CInternetSession](../../mfc/reference/cinternetsession-class.md) nesnesinden nesneye gönderilir. Bağlam tanımlayıcısını seçtiğiniz bir değere ayarlamak için varsayılanı geçersiz kılabilirsiniz. Bağlam tanımlayıcısı [CInternetSession döndürülür::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) ile tanımlanan nesne üzerinde durum sağlamak için. Makaleye bakın [Internet İlk Adımlar: WinInet](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi için.

### <a name="example"></a>Örnek

  Bu konunun daha önceki sınıf genel bakışındaki örneğe bakın.

## <a name="cftpfilefindfindfile"></a><a name="findfile"></a>CFtpFileFind::Dosya bul

Bir FTP dosyasını bulmak için bu üye işlevini arayın.

```
virtual BOOL FindFile(
    LPCTSTR pstrName = NULL,
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```

### <a name="parameters"></a>Parametreler

*pstrName*<br/>
Bulmak için dosyanın adını içeren bir dize için bir işaretçi. NULL ise, arama joker karakter araması (*) gerçekleştirir.

*Dwflags*<br/>
Bu oturumun nasıl işleyeceğini açıklayan bayraklar. Bu bayraklar bitwise OR işleci (&#124;) ile birleştirilebilir ve aşağıdaki gibidir:

- INTERNET_FLAG_RELOAD Yerel olarak önbelleğe alınmış olsa bile, verileri kablodan alın. Bu varsayılan bayraktır.

- INTERNET_FLAG_DONT_CACHE Verileri yerel olarak veya herhangi bir ağ geçidinde önbelleğe alma.

- INTERNET_FLAG_RAW_DATA ham verileri (FTP için [WIN32_FIND_DATA](/windows/win32/api/minwinbase/ns-minwinbase-win32_find_dataw) yapıları) döndürmek için varsayılan geçersiz kılın.

- INTERNET_FLAG_SECURE Emniyetli Soketler Katmanı veya PCT ile kablo üzerindeki işlemleri güvenli hale getirir. Bu bayrak yalnızca HTTP istekleri için geçerlidir.

- INTERNET_FLAG_EXISTING_CONNECT Mümkünse, her istek için yeni `FindFile` bir oturum oluşturmak yerine sunucuya varolan bağlantıları yeni istekler için yeniden kullanın.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Genişletilmiş hata bilgilerini almak için Win32 işlevini [getLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)arayın.

### <a name="remarks"></a>Açıklamalar

İlk `FindFile` FTP dosyasını almak için aradıktan sonra, sonraki FTP dosyalarını almak için [FindNextFile'ı](#findnextfile) arayabilirsiniz.

### <a name="example"></a>Örnek

  Bu konudaki önceki örneğe bakın.

## <a name="cftpfilefindfindnextfile"></a><a name="findnextfile"></a>CFtpFileFind::FindNextFile

[FindFile](#findfile) üye işlevini arayarak başlayan dosya aramasına devam etmek için bu üye işlevini arayın.

```
virtual BOOL FindNextFile();
```

### <a name="return-value"></a>Dönüş Değeri

Daha fazla dosya varsa sıfır olmayan; bulunan dosya dizindeki son dosyaysa veya bir hata oluştuysa sıfır. Genişletilmiş hata bilgilerini almak için Win32 işlevini [getLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)arayın. Bulunan dosya dizindeki son dosyaysa veya eşleşen dosya bulunamazsa, `GetLastError` işlev ERROR_NO_MORE_FILES döndürür.

### <a name="remarks"></a>Açıklamalar

Herhangi bir öznitelik işlevini aramadan önce bu işlevi en az bir kez aramalısınız [(bkz. CFileFind::FindNextFile).](../../mfc/reference/cfilefind-class.md#findnextfile)

`FindNextFile`Win32 işlevini [BulurİleriDosya'yu](/windows/win32/api/fileapi/nf-fileapi-findnextfilew)sarar.

### <a name="example"></a>Örnek

  Bu konunun önceki örneğine bakın.

## <a name="cftpfilefindgetfileurl"></a><a name="getfileurl"></a>CFtpFileFind::GetFileURL

Belirtilen dosyanın URL'sini almak için bu üye işlevini arayın.

```
CString GetFileURL() const;
```

### <a name="return-value"></a>Dönüş Değeri

Evrensel Kaynak Bulucu'nun (URL) dosya ve yolu.

### <a name="remarks"></a>Açıklamalar

`GetFileURL`üye işlevi [CFileFind benzer::GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath), formda `ftp://moose/dir/file.txt`URL döndürür dışında .

## <a name="see-also"></a>Ayrıca bkz.

[CFileFind Sınıfı](../../mfc/reference/cfilefind-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind Sınıf](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CInternetFile Sınıfı](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherFile Sınıfı](../../mfc/reference/cgopherfile-class.md)<br/>
[Chttpfile Sınıfı](../../mfc/reference/chttpfile-class.md)
