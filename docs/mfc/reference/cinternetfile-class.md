---
title: CInternetFile Sınıfı
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
ms.openlocfilehash: e3f1a7167f5464423754951764c4441513197841
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372396"
---
# <a name="cinternetfile-class"></a>CInternetFile Sınıfı

Internet protokollerini kullanan uzak sistemlerdeki dosyalara erişim sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CInternetFile : public CStdioFile
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CInternetFile::CInternetFile](#cinternetfile)|Bir `CInternetFile` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CInternetFile::İptal](#abort)|Tüm uyarıları ve hataları yoksayarak dosyayı kapatır.|
|[CInternetFile::Kapat](#close)|A'yı `CInternetFile` kapatır ve kaynaklarını serbest sağlar.|
|[CInternetFile::Flush](#flush)|Yazma arabelleği içeriğini temizler ve bellekteki verilerin hedef makineye yazıldığından emin olur.|
|[CInternetFile::GetLength](#getlength)|Dosyaboyutunu döndürür.|
|[CInternetFile::Oku](#read)|Belirtilen bayt sayısını okur.|
|[CInternetFile::ReadString](#readstring)|Bir karakter akışı okur.|
|[CInternetFile::Seek](#seek)|İşaretçiyi açık bir dosyada yeniden konumlandırın.|
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|Verilerin okunacağı arabelleğe boyutunu ayarlar.|
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|Verilerin yazılacağı arabelleğe boyutunu ayarlar.|
|[CInternetFile::Yaz](#write)|Belirtilen bayt sayısını yazar.|
|[CInternetFile::WriteString](#writestring)|Dosyaya null-sonlandırılan dize yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CInternetFile::operatör HINTERNET](#operator_hinternet)|Internet tutamacı için döküm operatörü.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CInternetFile::m_hFile](#m_hfile)|Dosyanın tutamacı.|

## <a name="remarks"></a>Açıklamalar

CHttpFile ve [CGopherFile](../../mfc/reference/chttpfile-class.md) dosya sınıfları için bir taban sınıf sağlar. [CGopherFile](../../mfc/reference/cgopherfile-class.md) Hiçbir `CInternetFile` nesneyi doğrudan oluşturmazsınız. Bunun yerine, [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) veya [CHttpConnection::OpenRequest'ı](../../mfc/reference/chttpconnection-class.md#openrequest)arayarak türetilmiş sınıflarından birinin nesnesini oluşturun. Ayrıca `CInternetFile` [CFtpConnection::OpenFile'ı](../../mfc/reference/cftpconnection-class.md#openfile)arayarak bir nesne oluşturabilirsiniz.

Üye `CInternetFile` `Open`işlevler `LockRange` `UnlockRange`, `Duplicate` , , , `CInternetFile`ve için uygulanmaz. Bu işlevleri bir `CInternetFile` nesne üzerinde çağırırsanız, [cnotsupportedException](../../mfc/reference/cnotsupportedexception-class.md)alırsınız.

Diğer MFC `CInternetFile` Internet sınıfları ile nasıl çalıştığı hakkında daha fazla bilgi edinmek için [WinInet ile internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfile](../../mfc/reference/cfile-class.md)

[Cstdiofile](../../mfc/reference/cstdiofile-class.md)

`CInternetFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxinet.h

## <a name="cinternetfileabort"></a><a name="abort"></a>CInternetFile::İptal

Bu nesneyle ilişkili dosyayı kapatır ve dosyayı okuma veya yazma için kullanılamaz hale getirir.

```
virtual void Abort();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi yok etmeden önce dosyayı kapatmadıysanız, yıkıcı dosyayı sizin için kapatır.

Özel durumları işlerken, `Abort` Iki önemli şekilde [Kapat'tan](#close) farklıdır. İlk olarak, `Abort` işlev hataları yoksayılduğu için hatalar adamıyor. İkinci `Abort` olarak, dosya açılmamışsa veya daha önce kapatılmışsa **Assert** etmez.

## <a name="cinternetfilecinternetfile"></a><a name="cinternetfile"></a>CInternetFile::CInternetFile

Bir `CInternetFile` nesne oluşturulduğunda bu üye işlev çağrılır.

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

*hFile*<br/>
Bir Internet dosyasının tutamacı.

*pstrFileName*<br/>
Dosya adını içeren bir dize için işaretçi.

*pBağlantı*<br/>
[CInternetConnection](../../mfc/reference/cinternetconnection-class.md) nesnesine işaretçi.

*bReadMode*<br/>
Dosyanın salt okunur olup olmadığını gösterir.

*hSession*<br/>
Internet oturumuiçin bir tanıtıcı.

*pstrServer*<br/>
Sunucunun adını içeren bir dize için bir işaretçi.

*dwBağlam*<br/>
Nesneiçin bağlam tanımlayıcısı. `CInternetFile` Bağlam tanımlayıcısı hakkında daha fazla bilgi için [WinInet Basics'e](../../mfc/wininet-basics.md) bakın.

### <a name="remarks"></a>Açıklamalar

Hiçbir `CInternetFile` nesneyi doğrudan oluşturmazsınız. Bunun yerine, [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) veya [CHttpConnection::OpenRequest'ı](../../mfc/reference/chttpconnection-class.md#openrequest)arayarak türetilmiş sınıflarından birinin nesnesini oluşturun. Ayrıca `CInternetFile` [CFtpConnection::OpenFile'ı](../../mfc/reference/cftpconnection-class.md#openfile)arayarak bir nesne oluşturabilirsiniz.

## <a name="cinternetfileclose"></a><a name="close"></a>CInternetFile::Kapat

A'yı `CInternetFile` kapatır ve kaynaklarından herhangi birini serbest klar.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Dosya yazıiçin açılmışsa, tüm arabelleğe alınan verilerin ana bilgisayara yazıldığından emin olmak için [Flush'a](#flush) üstü kapalı bir çağrı yapılır. Bir dosyayı kullanmayı bitirdiğinizde aramalısınız. `Close`

## <a name="cinternetfileflush"></a><a name="flush"></a>CInternetFile::Flush

Yazma arabelleği içeriğini temizlemek için bu üye işlevi arayın.

```
virtual void Flush();
```

### <a name="remarks"></a>Açıklamalar

Bellekteki tüm verilerin hedef makineye gerçekten yazıldığından emin olmak ve ana makineyle işleminizin tamamlandığından emin olmak için kullanın. `Flush` `Flush`yalnızca yazıiçin `CInternetFile` açılan nesneler üzerinde etkilidir.

## <a name="cinternetfilegetlength"></a><a name="getlength"></a>CInternetFile::GetLength

Dosyaboyutunu döndürür.

```
virtual ULONGLONG GetLength() const;
```

## <a name="cinternetfilem_hfile"></a><a name="m_hfile"></a>CInternetFile::m_hFile

Bu nesneyle ilişkili dosyanın tutamacı.

```
HINTERNET m_hFile;
```

## <a name="cinternetfileoperator-hinternet"></a><a name="operator_hinternet"></a>CInternetFile::operatör HINTERNET

Geçerli Internet oturumu için Windows tanıtıcısını almak için bu işleci kullanın.

```
operator HINTERNET() const;
```

## <a name="cinternetfileread"></a><a name="read"></a>CInternetFile::Oku

Verilen belleğe okumak için bu üye işlevi arayın, *lpvBuf*başlayarak , bayt belirtilen sayıda, *nCount*.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Dosya verilerinin okunduğu bellek adresine işaretçi.

*nSayısı*<br/>
Yazılacak bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Arabelleğe aktarılan bayt sayısı. Dosya sonuna ulaşıldıysa, iade değeri *nCount'den* küçük olabilir.

### <a name="remarks"></a>Açıklamalar

İşlev, dosya sona erdiğinde *nCount'den* daha az olabilecek bir sayı olan, gerçekte okunan bayt sayısını döndürür. Dosyayı okurken bir hata oluşursa, işlev hatayı açıklayan bir [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi atar. Dosyanın sonundan geçen okumanın hata olarak kabul edilmeyeceğini ve özel durum atılacağını unutmayın.

Tüm verilerin alınmasını sağlamak için, yöntem sıfır `CInternetFile::Read` döndürene kadar bir uygulama yöntemi aramaya devam etmelidir.

## <a name="cinternetfilereadstring"></a><a name="readstring"></a>CInternetFile::ReadString

Yeni bir çizgi karakteri bulana kadar bir karakter akışını okumak için bu üye işlevi arayın.

```
virtual BOOL ReadString(CString& rString);

virtual LPTSTR ReadString(
    LPTSTR pstr,
    UINT nMax);
```

### <a name="parameters"></a>Parametreler

*pstr*<br/>
Okunan satırı alacak bir dize için bir işaretçi.

*nMax*<br/>
Okunacak maksimum karakter sayısı.

*rString*<br/>
Okuma satırını alan [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

[CInternetFile](../../mfc/reference/cinternetfile-class.md) nesnesinden alınan düz verileri içeren arabellek için bir işaretçi. Bu yönteme geçirilen arabelleğin veri türüne bakılmaksızın, veriler üzerinde herhangi bir düzenleme gerçekleştirmez (örneğin, Unicode'a dönüştürme), bu nedenle döndürülen **verileri, geçersiz** <strong>\*</strong> tür döndürülmüş gibi beklediğiniz yapıyla eşlemelisiniz.

Dosya sonu herhangi bir veri okumadan ulaşıldıysa NULL; veya, boolean ise, FALSE dosya sonu herhangi bir veri okumadan ulaşıldı.

### <a name="remarks"></a>Açıklamalar

İşlev, elde edilen satırı *pstr* parametresi tarafından başvurulan belleğe yerleştirir. *NMax*tarafından belirtilen maksimum karakter sayısına ulaştığında karakterleri okumayı durdurur. Arabellek her zaman sonlandırıcı bir null karakter alır.

`ReadString` [SetReadBufferSize'ı](#setreadbuffersize)ilk aramadan ararsanız, 4096 baytlık bir arabellek alırsınız.

## <a name="cinternetfileseek"></a><a name="seek"></a>CInternetFile::Seek

İşaretçiyi daha önce açılmış bir dosyada yeniden konumlandırmak için bu üye işlevi arayın.

```
virtual ULONGLONG Seek(
    LONGLONG lOffset,
    UINT nFrom);
```

### <a name="parameters"></a>Parametreler

*lOffset*<br/>
Dosyadaki okuma/yazma işaretçisini taşımak için baytlar halinde mahsup edin.

*nKaynak*<br/>
Ofset için göreli başvuru. Aşağıdaki değerlerden biri olmalıdır:

- `CFile::begin`Dosya işaretçisi *lOff* baytlarını dosyanın başından ileri taşıyın.

- `CFile::current`Dosya işaretçisi *lOff* baytlarını dosyadaki geçerli konumdan taşıyın.

- `CFile::end`Dosya işaretçisi *lOff* baytlarını dosyanın sonundan taşıyın. *lOff* varolan dosyaya aramak için negatif olmalıdır; pozitif değerler dosyanın sonuna kadar arayacaktır.

### <a name="return-value"></a>Dönüş Değeri

İstenen pozisyon yasal sayılsa, dosyanın başından itibaren yeni bayt mahsup; aksi takdirde, değer tanımsız ve bir [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi atılır.

### <a name="remarks"></a>Açıklamalar

İşlev, `Seek` işaretçiyi kesinlikle veya göreli olarak belirli bir miktarda taşıyarak dosyanın içeriğine rasgele erişime izin verir. Arama sırasında hiçbir veri aslında okunmaz.

Şu anda, bu üye işleviçin bir çağrı yalnızca `CHttpFile` nesnelerle ilişkili veriler için desteklenir. FTP veya gopher istekleri için desteklenmez. Bu desteklenmeyen hizmetlerden birini ararsanız, `Seek` ERROR_INTERNET_INVALID_OPERATION Win32 hata koduna geri geçer.

Bir dosya açıldığında, dosya işaretçisi dosyanın başında 0 ofset olduğunu.

> [!NOTE]
> `Seek` Kullanma, [Flush'a](#flush)örtülü bir çağrı neden olabilir.

### <a name="example"></a>Örnek

  Taban sınıf uygulaması için örneğe bakın ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek)).

## <a name="cinternetfilesetreadbuffersize"></a><a name="setreadbuffersize"></a>CInternetFile::SetReadBufferSize

Türetilmiş bir `CInternetFile`nesne tarafından kullanılan geçici okuma arabelleği boyutunu ayarlamak için bu üye işlevi çağırın.

```
BOOL SetReadBufferSize(UINT nReadSize);
```

### <a name="parameters"></a>Parametreler

*nReadSize*<br/>
Baytlarda istenen tampon boyutu.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Altta yatan WinInet API'leri arabelleğe alma gerçekleştirmez, bu nedenle okunacak veri miktarına bakılmaksızın uygulamanızın verileri verimli bir şekilde okumasını sağlayan bir arabellek boyutu seçin. [Normalde Read](#read) için yapılan her arama büyük bir veri aount içeriyorsa (örneğin, dört veya daha fazla kilobayt), bir arabellek gerekmez. Ancak, küçük `Read` veri yığınları almak için ararsanız veya [readString'i](#readstring) tek tek satırları tek tek okumak için kullanırsanız, okuma arabelleği uygulama performansını artırır.

Varsayılan olarak, `CInternetFile` bir nesne okuma için herhangi bir arabellek sağlamaz. Bu üye işlevini ararsanız, dosyanın okuma erişimi için açıldığından emin olmalısınız.

Arabellek boyutunu istediğiniz zaman artırabilirsiniz, ancak arabellek küçültme hiçbir etkisi olmayacaktır. [ReadString'i](#readstring) ilk aramadan `SetReadBufferSize`ararsanız, 4096 baytlık bir arabellek alırsınız.

## <a name="cinternetfilesetwritebuffersize"></a><a name="setwritebuffersize"></a>CInternetFile::SetWriteBufferSize

Türetilmiş bir `CInternetFile`nesne tarafından kullanılan geçici yazma arabelleği boyutunu ayarlamak için bu üye işlevi arayın.

```
BOOL SetWriteBufferSize(UINT nWriteSize);
```

### <a name="parameters"></a>Parametreler

*nWriteSize*<br/>
Baytlarda arabelleğen boyutu.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0. Arama başarısız olursa, hatanın nedenini belirlemek için Win32 işlevi [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) çağrılabilir.

### <a name="remarks"></a>Açıklamalar

Altta yatan WinInet API'leri arabelleğe alma gerçekleştirmez, bu nedenle uygulamanızın yazılması gereken veri miktarına bakılmaksızın verimli bir şekilde veri yazmasına olanak tanıyan bir arabellek boyutu seçin. [Yazma'ya](#write) yapılan her arama normalde büyük miktarda veri içeriyorsa (örneğin, aynı anda dört veya daha fazla kilobayt), arabelleğe gerek duymamalıdır. Ancak, küçük veri yığınları yazmak için [Yaz'ı](#write) ararsanız, yazma arabelleği uygulamanızın performansını artırır.

Varsayılan olarak, `CInternetFile` bir nesne yazmak için herhangi bir arabellek sağlamaz. Bu üye işlevini ararsanız, dosyanın yazma erişimi için açıldığından emin olmalısınız. Yazma arabelleği boyutunu istediğiniz zaman değiştirebilirsiniz, ancak bunu yapmak [Flush'a](#flush)örtülü bir çağrıya neden olur.

## <a name="cinternetfilewrite"></a><a name="write"></a>CInternetFile::Yaz

Verilen belleğe, *lpvBuf'a,* belirtilen bayt sayısına, *nCount'e*yazmak için bu üye işlevi arayın.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parametreler

*lpBuf*<br/>
Yazılacak ilk bayt için bir işaretçi.

*nSayısı*<br/>
Yazılacak bayt sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Verileri yazarken herhangi bir hata oluşursa, işlev hatayı açıklayan bir [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi atar.

## <a name="cinternetfilewritestring"></a><a name="writestring"></a>CInternetFile::WriteString

Bu işlev, ilişkili dosyaya null-sonlandırılan dize yazar.

```
virtual void WriteString(LPCTSTR pstr);
```

### <a name="parameters"></a>Parametreler

*pstr*<br/>
Yazılacak içeriği içeren bir dize için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Verileri yazarken herhangi bir hata oluşursa, işlev hatayı açıklayan bir [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi atar.

## <a name="see-also"></a>Ayrıca bkz.

[CStdioFile Sınıfı](../../mfc/reference/cstdiofile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)
