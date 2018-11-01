---
title: Cınternetfile sınıfı
ms.date: 11/04/2016
f1_keywords:
- CInternetFile
- AFXINET/CInternetFile
- AFXINET/CInternetFile::CInternetFile
- AFXINET/CInternetFile::Abort
- AFXINET/CInternetFile::Close
- AFXINET/CInternetFile::Flush
- AFXINET/CInternetFile::GetLength
- AFXINET/CInternetFile::Read
- AFXINET/CInternetFile::ReadString
- AFXINET/CInternetFile::Seek
- AFXINET/CInternetFile::SetReadBufferSize
- AFXINET/CInternetFile::SetWriteBufferSize
- AFXINET/CInternetFile::Write
- AFXINET/CInternetFile::WriteString
- AFXINET/CInternetFile::m_hFile
helpviewer_keywords:
- CInternetFile [MFC], CInternetFile
- CInternetFile [MFC], Abort
- CInternetFile [MFC], Close
- CInternetFile [MFC], Flush
- CInternetFile [MFC], GetLength
- CInternetFile [MFC], Read
- CInternetFile [MFC], ReadString
- CInternetFile [MFC], Seek
- CInternetFile [MFC], SetReadBufferSize
- CInternetFile [MFC], SetWriteBufferSize
- CInternetFile [MFC], Write
- CInternetFile [MFC], WriteString
- CInternetFile [MFC], m_hFile
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
ms.openlocfilehash: 309d4210f72f7ecd83ed6a8eb79874a1c8170d59
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586881"
---
# <a name="cinternetfile-class"></a>Cınternetfile sınıfı

Internet protokolleri kullanan uzak sistemlerdeki dosyalara erişimi sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CInternetFile : public CStdioFile
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInternetFile::CInternetFile](#cinternetfile)|Oluşturur bir `CInternetFile` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetFile::Abort](#abort)|Tüm uyarıları ve hataları yoksayma dosyayı kapatır.|
|[CInternetFile::Close](#close)|Kapatan bir `CInternetFile` ve kaynaklarını serbest bırakır.|
|[CInternetFile::Flush](#flush)|Yazma arabelleğini içeriğini temizler ve bellek verileri hedef makineye yazılır emin olur.|
|[CInternetFile::GetLength](#getlength)|Dosyanın boyutu döndürür.|
|[CInternetFile::Read](#read)|Belirtilen bayt sayısını okur.|
|[CInternetFile::ReadString](#readstring)|Bir karakter akışı okur.|
|[CInternetFile::Seek](#seek)|İşaretçi de açık bir dosyayı yeniden konumlandırır.|
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|Verilerin okunacağı arabellek boyutunu ayarlar.|
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|Verilerin yazılacağı arabellek boyutunu ayarlar.|
|[CInternetFile::Write](#write)|Belirtilen bayt yazar.|
|[CInternetFile::WriteString](#writestring)|Null ile sonlandırılmış bir dize bir dosyaya yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetFile::operator HINTERNET](#operator_hinternet)|Atama işleci için bir Internet tanıtıcısı.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CInternetFile::m_hFile](#m_hfile)|Bir dosyaya tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

İçin bir temel sınıf sağlar [CHttpFile](../../mfc/reference/chttpfile-class.md) ve [CGopherFile](../../mfc/reference/cgopherfile-class.md) dosya sınıfları. Asla oluşturma bir `CInternetFile` doğrudan nesne. Bunun yerine, çağırarak türetilmiş sınıflarının biri bir nesne oluşturma [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) veya [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Ayrıca oluşturabileceğiniz bir `CInternetFile` çağırarak [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).

`CInternetFile` Üye işlevleri `Open`, `LockRange`, `UnlockRange`, ve `Duplicate` için uygulanmadı `CInternetFile`. Bu işlevler çağırırsanız bir `CInternetFile` nesnesi elde edersiniz bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

Hakkında daha fazla bilgi edinmek için `CInternetFile` diğer Internet MFC sınıfları ile çalışır, başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

`CInternetFile`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxinet.h

##  <a name="abort"></a>  CInternetFile::Abort

Bu nesneyle ilişkili dosyayı kapatır ve dosyanın okuma veya yazma için kullanılabilir hale getirir.

```
virtual void Abort();
```

### <a name="remarks"></a>Açıklamalar

Dosya nesne yok etme öncesinde kapatılmamış, yok edici sizin için kapatılır.

Özel durumlar, işlerken `Abort` farklıdır [Kapat](#close) iki önemli şekilde. İlk olarak, `Abort` işlevi değil bir özel durum oluşturur hataları nedeniyle, hataları yoksayar. İkinci olarak, `Abort` yok **ASSERT** dosya açılmamış olan ya da daha önce kapatıldı.

##  <a name="cinternetfile"></a>  CInternetFile::CInternetFile

Bu üye işlevi aldığında çağrılan bir `CInternetFile` nesnesi oluşturulur.

```
CInternetFile(
    HINTERNET hFile,
    LPCTSTR pstrFileName,
    CInternetConnection* pConnection,
    BOOL bReadMode);

CInternetFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrFileName,
    LPCTSTR pstrServer,
    DWORD_PTR dwContext,
    BOOL bReadMode);
```

### <a name="parameters"></a>Parametreler

*Hfıle*<br/>
Bir Internet dosyaya tanıtıcı.

*pstrFileName*<br/>
Dosya adını içeren bir dize işaretçisi.

*pConnection*<br/>
Bir işaretçi bir [Cınternetconnection](../../mfc/reference/cinternetconnection-class.md) nesne.

*bReadMode*<br/>
Dosyanın salt okunur olup olmadığını gösterir.

*hSession*<br/>
Bir Internet oturumu için bir tanıtıcı.

*pstrServer*<br/>
Sunucu adını içeren bir dize işaretçisi.

*dwContext*<br/>
İçerik tanımlayıcısı `CInternetFile` nesne. Bkz: [WinINet Temelleri](../../mfc/wininet-basics.md) bağlam tanımlayıcısı hakkında daha fazla bilgi.

### <a name="remarks"></a>Açıklamalar

Asla oluşturma bir `CInternetFile` doğrudan nesne. Bunun yerine, çağırarak türetilmiş sınıflarının biri bir nesne oluşturma [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) veya [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Ayrıca oluşturabileceğiniz bir `CInternetFile` çağırarak [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).

##  <a name="close"></a>  CInternetFile::Close

Kapatan bir `CInternetFile` ve tüm kaynaklarını serbest bırakır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Dosya yazma için açılmış, örtük çağrıyla yoktur [Temizleme](#flush) tüm veri arabelleğe güvence altına almak için ana bilgisayara yazılır. Çağırmalısınız `Close` dosya kullanmayı bitirdiğinizde.

##  <a name="flush"></a>  CInternetFile::Flush

Yazma arabelleğini içeriğini temizlemek için bu üye işlevini çağırın.

```
virtual void Flush();
```

### <a name="remarks"></a>Açıklamalar

Kullanım `Flush` bellekteki tüm verileri gerçekte yazıldı, hedef makineye güvence altına alır ve ana makine ile işlem tamamlanmış güvence altına almak için. `Flush` Yalnızca üzerinde etkili olan `CInternetFile` nesneleri, yazma için açılmış.

##  <a name="getlength"></a>  CInternetFile::GetLength

Dosyanın boyutu döndürür.

```
virtual ULONGLONG GetLength() const;
```

##  <a name="m_hfile"></a>  CInternetFile::m_hFile

Bu nesneyle ilişkili dosyaya tanıtıcı.

```
HINTERNET m_hFile;
```

##  <a name="operator_hinternet"></a>  CInternetFile::operator HINTERNET

Windows tanıtıcı için geçerli Internet oturumu almak için bu işleci kullanın.

```
operator HINTERNET() const;
```

##  <a name="read"></a>  CInternetFile::Read

Verilen belleğe başlayarak okumak için bu üye işlevi çağrısı *lpvBuf*, bayt sayısı belirtilen *nCount*.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Hangi dosyaya veriler okunur bir bellek adresi için bir işaretçi.

*nCount*<br/>
Yazılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Arabelleğe aktarılan bayt sayısı. Dönüş değeri olabilir küçüktür *nCount* , dosya sonuna ulaşıldı.

### <a name="remarks"></a>Açıklamalar

İşlevi gerçekten okunan bayt sayısını döndürür; olabilecek birtakım küçüktür *nCount* dosya sona ererse. Dosya okunurken bir hata meydana gelirse, işlev oluşturur. bir [Cınternetexception](../../mfc/reference/cinternetexception-class.md) hatayı tanımlayan nesne. Dosyanın sonundan okunurken bir hata olarak kabul edilmez ve hiçbir özel durum unutmayın.

Tüm veriler alınır emin olmak için uygulamanın çağırmaya devam gerekir `CInternetFile::Read` sıfır yöntemi dönene kadar yöntemi.

##  <a name="readstring"></a>  CInternetFile::ReadString

Yeni satır karakteri bulana kadar karakterleri bir akışını okumak için bu üye işlevini çağırın.

```
virtual BOOL ReadString(CString& rString);

virtual LPTSTR ReadString(
    LPTSTR pstr,
    UINT nMax);
```

### <a name="parameters"></a>Parametreler

*pstr*<br/>
Okunan satır alacak bir dizeye bir işaretçi.

*nMax*<br/>
Okunacak karakter sayısı.

*rString*<br/>
Bir başvuru [CString](../../atl-mfc-shared/reference/cstringt-class.md) okuma satırın alan nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Arabelleğe alınan düz veriler içeren bir işaretçi [Cınternetfile](../../mfc/reference/cinternetfile-class.md) nesne. Bu yönteme geçirilen arabellek veri türünden bağımsız olarak, tüm işlemeleri (örneğin, Unicode dönüştürme) veri çubuğunda gerçekleştirmez, döndürülen veri yapısına eşlemeniz gerekir böylece beklediğiniz gibi **void** <strong>\*</strong> türü döndürüldü.

Dosya sonu herhangi bir veri okumadan ulaştıysanız NULL; veya, boolean, dosya sonu ise FALSE herhangi bir veri okumadan ulaşıldı.

### <a name="remarks"></a>Açıklamalar

Sonuçta elde edilen satırı işlevi tarafından başvurulan belleği yerleştirir *pstr* parametresi. Karakterleri okuma durdurur tarafından belirtilen karakter sayısı ulaştığında *nMax*. Arabellek her zaman Sonlandırıcı null karakterini alır.

Eğer `ReadString` ilk çağırmadan [SetReadBufferSize](#setreadbuffersize), 4096 baytlık bir arabellek alırsınız.

##  <a name="seek"></a>  CInternetFile::Seek

İşaretçi önceden açılmış bir dosyaya yeniden konumlandırmak için bu üye işlevini çağırın.

```
virtual ULONGLONG Seek(
    LONGLONG lOffset,
    UINT nFrom);
```

### <a name="parameters"></a>Parametreler

*lOffset*<br/>
Dosyada okuma/yazma işaretçiyi için bayt cinsinden uzaklığı.

*nFrom*<br/>
Göreli başvuru için uzaklık. Aşağıdaki değerlerden biri olmalıdır:

- `CFile::begin` Dosya işaretçiyi *lOff* dosyanın başından itibaren bayt iletin.

- `CFile::current` Dosya işaretçiyi *lOff* dosyasındaki geçerli konumdan bayt.

- `CFile::end` Dosya işaretçiyi *lOff* dosyasının sonuna gelen baytlar. *lOff* gerekir olması negatif mevcut aranacak dosya; pozitif değerleri, dosyanın sonundan arama.

### <a name="return-value"></a>Dönüş Değeri

Yeni bayt; istenen konumu yasal ise dosyanın başından uzaklığı Aksi takdirde, değeri tanımsızdır ve [Cınternetexception](../../mfc/reference/cinternetexception-class.md) nesnesi oluşturulur.

### <a name="remarks"></a>Açıklamalar

`Seek` İşlevi erişme izni verir rastgele bir dosyanın içeriğini hareket ettirerek işaretçinin belirtilen bir miktarı mutlak veya göreceli olarak. Veri yok, arama sırasında gerçekten okuyun.

Şu anda bu üye işlevine bir çağrı yalnızca ilişkili verileri desteklenir `CHttpFile` nesneleri. FTP veya gopher istekler için desteklenmiyor. Eğer `Seek` desteklenmeyen Bu hizmetlerden biri için geri, Win32 hata kodu ERROR_INTERNET_INVALID_OPERATION geçer.

Bir dosya açıldığında, dosyanın konumu 0 ' dosyasının başında işaretçisidir.

> [!NOTE]
>  Kullanarak `Seek` örtük çağrıyla neden [Temizleme](#flush).

### <a name="example"></a>Örnek

  Temel sınıf uygulamasına için örneğe bakın ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek)).

##  <a name="setreadbuffersize"></a>  CInternetFile::SetReadBufferSize

Tarafından kullanılan geçici okuma arabelleğinin boyutunu ayarlamak için bu üye işlevi çağrısı bir `CInternetFile`-türetilmiş bir nesneye.

```
BOOL SetReadBufferSize(UINT nReadSize);
```

### <a name="parameters"></a>Parametreler

*nReadSize*<br/>
İstenen arabellek boyutu bayt cinsinden.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Temel alınan WinINet API'leri değil arabelleğe alma gerçekleştirin, böylece verileri verimli bir şekilde okunması gereken veri miktarı bağımsız olarak okumak için uygulamanıza izin veren bir arabellek boyutu seçin. Her çağırırsanız [okuma](#read) normalde büyük aount içerir verilerinin (örneğin, dört veya daha fazla kilobayt), bir arabellek yapmanız gerekmez. Ancak, çağırırsanız `Read` verileri küçük öbeklere almak veya kullanıyorsanız [ReadString'i](#readstring) Okuma arabelleği uygulama performansını artıran sonra bir defada tek satır okumak için.

Varsayılan olarak, bir `CInternetFile` nesne için Okuma arabelleği sağlamaz. Bu üye işlevini çağırın, dosya için okuma erişimi açılmış emin olmanız gerekir.

Herhangi bir zamanda arabellek boyutunu artırabilir, ancak arabellek küçültme hiçbir etkisi olmaz. Eğer [ReadString'i](#readstring) ilk çağırmadan `SetReadBufferSize`, 4096 baytlık bir arabellek alırsınız.

##  <a name="setwritebuffersize"></a>  CInternetFile::SetWriteBufferSize

Tarafından kullanılan geçici yazma arabellek boyutunu ayarlamak için bu üye işlevi çağrısı bir `CInternetFile`-türetilmiş bir nesneye.

```
BOOL SetWriteBufferSize(UINT nWriteSize);
```

### <a name="parameters"></a>Parametreler

*nWriteSize*<br/>
Arabelleğin bayt cinsinden boyutu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0. Çağrı başarısız olursa, Win32 işlevini [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.

### <a name="remarks"></a>Açıklamalar

WinINet API'leri yok gerçekleştirmek arabelleğe alma, temel alınan verimli bir şekilde yazılacak veri miktarından bağımsız olarak veri yazmak uygulamanızın izin veren bir arabellek boyutu için seçin. Her çağırırsanız [yazma](#write) genellikle büyük bir miktarını içerir verilerinin (örneğin, dört veya daha fazla kilobayt teker teker), bir arabellek yapmanız gerekmez. Ancak, eğer [yazma](#write) küçük öbekler halinde veri yazmak için bir yazma arabelleği uygulamanızın performansını artırır.

Varsayılan olarak, bir `CInternetFile` nesne yazmak için arabelleğe sağlamaz. Bu üye işlevini çağırın, dosya yazma erişimi için açılmış emin olmanız gerekir. Yazma arabellek boyutu dilediğiniz zaman değiştirebilirsiniz, ancak bunu yapmanız bu nedenle örtük çağrıyla neden [Temizleme](#flush).

##  <a name="write"></a>  CInternetFile::Write

Verilen belleğe yazmak için bu üye işlevi çağrısı *lpvBuf*, bayt sayısı belirtilen *nCount*.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Yazılacak ilk baytına bir işaretçi.

*nCount*<br/>
Yazılacak bayt sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Veriler yazılırken bir hata meydana gelirse, işlev oluşturur. bir [Cınternetexception](../../mfc/reference/cinternetexception-class.md) hatayı tanımlayan nesne.

##  <a name="writestring"></a>  CInternetFile::WriteString

Bu işlev için ilişkili dosya null ile sonlandırılmış bir dize yazar.

```
virtual void WriteString(LPCTSTR pstr);
```

### <a name="parameters"></a>Parametreler

*pstr*<br/>
Yazılacak içeriği içeren bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Veriler yazılırken bir hata meydana gelirse, işlev oluşturur. bir [Cınternetexception](../../mfc/reference/cinternetexception-class.md) hatayı tanımlayan nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[CStdioFile Sınıfı](../../mfc/reference/cstdiofile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)
