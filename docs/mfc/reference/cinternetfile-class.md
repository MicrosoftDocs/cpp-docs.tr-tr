---
description: 'Daha fazla bilgi edinin: CInternetFile Class'
title: CInternetFile sınıfı
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
ms.openlocfilehash: 486b5869d0773351443a923ceef345591131036c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143487"
---
# <a name="cinternetfile-class"></a>CInternetFile sınıfı

Internet protokolleri kullanan uzak sistemlerdeki dosyalara erişim sağlar.

## <a name="syntax"></a>Syntax

```
class CInternetFile : public CStdioFile
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CInternetFile:: CInternetFile](#cinternetfile)|Bir `CInternetFile` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetFile:: Abort](#abort)|Tüm uyarıları ve hataları yoksayarak dosyayı kapatır.|
|[CInternetFile:: Close](#close)|Bir kapatır `CInternetFile` ve kaynaklarını serbest bırakır.|
|[CInternetFile:: Flush](#flush)|Yazma arabelleğinin içeriğini boşaltır ve bellekteki verilerin hedef makineye yazıldığından emin olur.|
|[CInternetFile:: GetLength](#getlength)|Dosyanın boyutunu döndürür.|
|[CInternetFile:: Read](#read)|Belirtilen bayt sayısını okur.|
|[CInternetFile:: ReadString](#readstring)|Bir karakter akışını okur.|
|[CInternetFile:: Seek](#seek)|Açık bir dosyadaki işaretçiyi konumlandırır.|
|[CInternetFile:: SetReadBufferSize](#setreadbuffersize)|Verilerin okunacağı arabelleğin boyutunu ayarlar.|
|[CInternetFile:: SetWriteBufferSize](#setwritebuffersize)|Verilerin yazılacağı arabelleğin boyutunu ayarlar.|
|[CInternetFile:: Write](#write)|Belirtilen bayt sayısını yazar.|
|[CInternetFile:: WriteString](#writestring)|Bir dosyaya null ile sonlandırılmış bir dize yazar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CInternetFile:: operator HıNTERNET](#operator_hinternet)|Internet tanıtıcısı için bir atama işleci.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CInternetFile:: m_hFile](#m_hfile)|Bir dosya için tanıtıcı.|

## <a name="remarks"></a>Açıklamalar

[CHttpFile](../../mfc/reference/chttpfile-class.md) ve [CGopherFile](../../mfc/reference/cgopherfile-class.md) dosya sınıfları için bir temel sınıf sağlar. Hiçbir şekilde doğrudan bir nesne oluşturmamanız gerekir `CInternetFile` . Bunun yerine, [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) veya [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest)' i çağırarak türetilmiş sınıflarından birinin bir nesnesini oluşturun. Ayrıca, `CInternetFile` [CFtpConnection:: OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)öğesini çağırarak bir nesne oluşturabilirsiniz.

`CInternetFile`Üye işlevleri,,, `Open` `LockRange` `UnlockRange` ve `Duplicate` için uygulanmaz `CInternetFile` . Bu işlevleri bir nesne üzerinde çağırırsanız `CInternetFile` , bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)alırsınız.

Diğer MFC Internet sınıflarıyla nasıl çalıştığı hakkında daha fazla bilgi edinmek için `CInternetFile` bkz. [Winınet Ile Internet programlama](../../mfc/win32-internet-extensions-wininet.md)makalesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

`CInternetFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFXINET. h

## <a name="cinternetfileabort"></a><a name="abort"></a> CInternetFile:: Abort

Bu nesneyle ilişkili dosyayı kapatır ve dosyayı okuma veya yazma için kullanılamaz hale getirir.

```
virtual void Abort();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi yok etmeden önce dosyayı kapatmamış, yıkıcı sizin için kapatır.

Özel durumları işlerken, `Abort` iki önemli şekilde [kapatmadan](#close) farklıdır. İlk olarak, `Abort` işlev hatalara aykırı bir durum oluşturmaz çünkü hata yoksayar. İkincisi, `Abort` Dosya açılmadıysa veya daha önce kapatılmışsa, bunu **yapmaz** .

## <a name="cinternetfilecinternetfile"></a><a name="cinternetfile"></a> CInternetFile:: CInternetFile

Bu üye işlevi, bir `CInternetFile` nesne oluşturulduğunda çağrılır.

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
Internet dosyası için bir tanıtıcı.

*pstrFileName*<br/>
Dosya adını içeren bir dize işaretçisi.

*pConnection*<br/>
[CInternetConnection](../../mfc/reference/cinternetconnection-class.md) nesnesine yönelik bir işaretçi.

*Enine mod*<br/>
Dosyanın salt okunurdur.

*hSession*<br/>
Bir Internet oturumu için tanıtıcı.

*pstrServer*<br/>
Sunucu adını içeren bir dize işaretçisi.

*dwContext*<br/>
Nesnenin bağlam tanımlayıcısı `CInternetFile` . Bağlam tanımlayıcısı hakkında daha fazla bilgi için bkz. [Winınet temelleri](../../mfc/wininet-basics.md) .

### <a name="remarks"></a>Açıklamalar

Hiçbir şekilde doğrudan bir nesne oluşturmamanız gerekir `CInternetFile` . Bunun yerine, [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) veya [CHttpConnection:: OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest)' i çağırarak türetilmiş sınıflarından birinin bir nesnesini oluşturun. Ayrıca, `CInternetFile` [CFtpConnection:: OpenFile](../../mfc/reference/cftpconnection-class.md#openfile)öğesini çağırarak bir nesne oluşturabilirsiniz.

## <a name="cinternetfileclose"></a><a name="close"></a> CInternetFile:: Close

Bir kapatır `CInternetFile` ve kaynaklarından herhangi birini boşaltır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Dosya yazmak üzere açılırsa, tüm arabelleğe alınmış verilerin konağa yazıldığını güvence altına almak için [temizlemeye](#flush) yönelik bir örtülü çağrı vardır. `Close`Bir dosya kullanmayı bitirdiğinizde ' i çağırmanız gerekir.

## <a name="cinternetfileflush"></a><a name="flush"></a> CInternetFile:: Flush

Yazma arabelleğinin içeriğini temizlemek için bu üye işlevi çağırın.

```
virtual void Flush();
```

### <a name="remarks"></a>Açıklamalar

`Flush`Bellekteki tüm verilerin gerçekten hedef makineye yazıldığını ve ana makine ile yaptığınız işlemin tamamlanmasını güvence altına almak için kullanın. `Flush` yalnızca `CInternetFile` yazma için açılmış nesneler üzerinde etkilidir.

## <a name="cinternetfilegetlength"></a><a name="getlength"></a> CInternetFile:: GetLength

Dosyanın boyutunu döndürür.

```
virtual ULONGLONG GetLength() const;
```

## <a name="cinternetfilem_hfile"></a><a name="m_hfile"></a> CInternetFile:: m_hFile

Bu nesneyle ilişkili dosya için bir tanıtıcı.

```
HINTERNET m_hFile;
```

## <a name="cinternetfileoperator-hinternet"></a><a name="operator_hinternet"></a> CInternetFile:: operator HıNTERNET

Geçerli Internet oturumu için Windows tanıtıcısını almak üzere bu işleci kullanın.

```
operator HINTERNET() const;
```

## <a name="cinternetfileread"></a><a name="read"></a> CInternetFile:: Read

Bu üye işlevini, *Lpvarabelleğe* başlayarak belirtilen belleğe okumak için çağırın, belirtilen sayıda bayt, *nCount*.

```
virtual UINT Read(
    void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parametreler

*Lparabelleğe*<br/>
Dosya verilerinin okunduğu bir bellek adresine yönelik bir işaretçi.

*nCount*<br/>
Yazılacak baytların sayısı.

### <a name="return-value"></a>Dönüş Değeri

Arabelleğe aktarılan baytların sayısı. Dosya sonuna ulaşılırsa dönüş değeri *nCount* 'tan daha az olabilir.

### <a name="remarks"></a>Açıklamalar

İşlev gerçekten okunan bayt sayısını döndürür; dosya sona erdiğinde *nCount* 'tan daha az olabilecek bir sayı olabilir. Dosya okunurken bir hata oluşursa, işlev hatayı açıklayan bir [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi oluşturur. Dosya sonunun ötesinde okuma bir hata olarak değerlendirilmediğini ve hiçbir özel durum oluşturulmayacak olduğunu unutmayın.

Tüm verilerin alındığından emin olmak için, `CInternetFile::Read` Yöntem sıfır döndürene kadar bir uygulamanın metodu çağırmaya devam etmesi gerekir.

## <a name="cinternetfilereadstring"></a><a name="readstring"></a> CInternetFile:: ReadString

Bir yeni satır karakteri bulana kadar bir karakter akışını okumak için bu üye işlevi çağırın.

```
virtual BOOL ReadString(CString& rString);

virtual LPTSTR ReadString(
    LPTSTR pstr,
    UINT nMax);
```

### <a name="parameters"></a>Parametreler

*PSTR*<br/>
Okunan satırı alacak bir dize işaretçisi.

*Ngünde en çok*<br/>
Okunacak maksimum karakter sayısı.

*rString*<br/>
Okuma satırını alan [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

[CInternetFile](../../mfc/reference/cinternetfile-class.md) nesnesinden alınan düz verileri içeren arabelleğin bir işaretçisi. Bu yönteme geçirilen arabelleğin veri türünden bağımsız olarak, veri üzerinde herhangi bir yürütme gerçekleştirmez (örneğin, Unicode 'a dönüştürme), bu nedenle döndürülen verileri, **`void`** tür döndürülmüş gibi, istediğiniz yapıya eşlemeniz gerekir <strong>\*</strong> .

Herhangi bir veri okunmadan dosya sonu ulaşılırsa NULL; ya da Boolean ise, herhangi bir veri okunmadan dosya sonu ulaşılırsa FALSE 'TUR.

### <a name="remarks"></a>Açıklamalar

İşlevi, elde edilen satırı *PSTR* parametresi tarafından başvurulan belleğe koyar. *NMAX* tarafından belirtilen en fazla karakter sayısına ulaştığında karakterleri okumayı durduruyor. Arabellek her zaman bir Sonlandırıcı null karakter alır.

`ReadString`Önce [SetReadBufferSize](#setreadbuffersize)çağrılmadan çağrı yaparsanız, 4096 baytlık bir arabellek alırsınız.

## <a name="cinternetfileseek"></a><a name="seek"></a> CInternetFile:: Seek

Daha önce açılmış bir dosyadaki işaretçiyi yeniden konumlandırmak için bu üye işlevi çağırın.

```
virtual ULONGLONG Seek(
    LONGLONG lOffset,
    UINT nFrom);
```

### <a name="parameters"></a>Parametreler

*Lkayması*<br/>
Okuma/yazma işaretçisini dosyada taşımak için bayt cinsinden fark.

*Ngüncelleştirmelerini*<br/>
Uzaklığın göreli başvurusu. Aşağıdaki değerlerden biri olmalıdır:

- `CFile::begin` Dosya *işaretçisini dosyanın* başlangıcından ileri doğru bir şekilde taşıyın.

- `CFile::current` Dosya *işaretçisini dosyada* bulunan geçerli konumdan taşıyın.

- `CFile::end` Dosya *işaretçisini dosyanın* sonundaki bir değerle taşıyın. *lOff* , mevcut dosyaya arama yapmak için negatif olmalıdır; pozitif değerler dosyanın sonundan daha sonra aranacaktır.

### <a name="return-value"></a>Dönüş Değeri

İstenen konum geçerli ise, yeni bayt, dosyanın başından itibaren kaydırılır; Aksi takdirde, değer tanımsızdır ve bir [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi oluşturulur.

### <a name="remarks"></a>Açıklamalar

`Seek`İşlevi, işaretçiyi belirtilen miktarda, kesinlikle veya görece taşıyarak bir dosyanın içeriğine rastgele erişime izin verir. Arama sırasında hiç veri okunmamıştır.

Şu anda, bu üye işlevine yapılan bir çağrı yalnızca nesnelerle ilişkili veriler için desteklenir `CHttpFile` . FTP veya Gopher istekleri için desteklenmez. `Seek`Bu desteklenmeyen hizmetlerden birini çağırırsanız, ERROR_INTERNET_INVALID_OPERATION Win32 hata koduna geri geçer.

Bir dosya açıldığında, dosya işaretçisi dosyanın başlangıcında 0 uzaklığında olur.

> [!NOTE]
> Kullanmak `Seek` örtük bir çağrının [temizlemeye](#flush)neden olabilir.

### <a name="example"></a>Örnek

  Temel sınıf uygulamasına yönelik örneğe bakın ( [CFile:: Seek](../../mfc/reference/cfile-class.md#seek)).

## <a name="cinternetfilesetreadbuffersize"></a><a name="setreadbuffersize"></a> CInternetFile:: SetReadBufferSize

Türetilmiş bir nesne tarafından kullanılan geçici okuma arabelleğinin boyutunu ayarlamak için bu üye işlevini çağırın `CInternetFile` .

```
BOOL SetReadBufferSize(UINT nReadSize);
```

### <a name="parameters"></a>Parametreler

*nReadSize*<br/>
İstenen arabellek boyutu (bayt).

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

Temeldeki WinInet API 'Leri arabelleğe alma işlemi yapmaz, bu nedenle, okunacak veri miktarına bakılmaksızın uygulamanızın verileri verimli bir şekilde okumasını sağlayan bir arabellek boyutu seçin. Her bir [okunan](#read) çağrı genellikle verilerin büyük bir Aoi (örneğin, dört veya daha fazla kilobayt) içeriyorsa, bir arabelleğe gerek kalmaz. Ancak, `Read` küçük veri öbeklerini almak için çağrı yaparsanız veya tek seferde ayrı satırları okumak Için [ReadString](#readstring) kullanırsanız, okuma arabelleği uygulama performansını geliştirir.

Varsayılan olarak, bir `CInternetFile` nesne okuma için herhangi bir arabelleğe alma sağlamaz. Bu üye işlevi çağırırsanız, dosyanın okuma erişimi için açıldığından emin olmanız gerekir.

Arabellek boyutunu dilediğiniz zaman artırabilirsiniz, ancak arabelleğin daraltılması hiçbir etkiye sahip olmaz. [ReadString](#readstring) 'i önce çağrılmadan çağırırsanız `SetReadBufferSize` , 4096 baytlık bir arabellek alırsınız.

## <a name="cinternetfilesetwritebuffersize"></a><a name="setwritebuffersize"></a> CInternetFile:: SetWriteBufferSize

Türetilmiş bir nesne tarafından kullanılan geçici yazma arabelleğinin boyutunu ayarlamak için bu üye işlevini çağırın `CInternetFile` .

```
BOOL SetWriteBufferSize(UINT nWriteSize);
```

### <a name="parameters"></a>Parametreler

*nWriteSize*<br/>
Arabelleğin bayt cinsinden boyutu.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0. Çağrı başarısız olursa, hatanın nedenini öğrenmek için WIN32 [Win32 işlevi çağrılabilir](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) .

### <a name="remarks"></a>Açıklamalar

Temeldeki WinInet API 'Leri arabelleğe alma işlemi yapmaz, bu nedenle uygulamanızın yazılacak veri miktarına bakılmaksızın verileri verimli bir şekilde yazmasını sağlayan bir arabellek boyutu seçin. Normal olarak [yazılacak](#write) her çağrı büyük miktarda veri içeriyorsa (örneğin, bir kerede dört veya daha fazla kilobayt), bir arabelleğe gerek kalmaz. Ancak, küçük veri öbeklerini yazmak için [Write](#write) çağrısı yaparsanız, yazma arabelleği uygulamanızın performansını geliştirir.

Varsayılan olarak, bir `CInternetFile` nesne yazma için herhangi bir arabelleğe alma sağlamaz. Bu üye işlevi çağırırsanız, dosyanın yazma erişimi için açıldığından emin olmanız gerekir. Yazma arabelleğinin boyutunu dilediğiniz zaman değiştirebilirsiniz, ancak bunu yapmak örtük çağrının [temizlenmesi](#flush)durumunda olur.

## <a name="cinternetfilewrite"></a><a name="write"></a> CInternetFile:: Write

Verilen belleğe, *Lpvarabelleğe*, belirtilen bayt sayısına ( *nCount*) yazmak için bu üye işlevi çağırın.

```
virtual void Write(
    const void* lpBuf,
    UINT nCount);
```

### <a name="parameters"></a>Parametreler

*Lparabelleğe*<br/>
Yazılacak ilk bayta yönelik bir işaretçi.

*nCount*<br/>
Yazılacak bayt sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Veriler yazılırken herhangi bir hata oluşursa, işlev hatayı açıklayan bir [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi oluşturur.

## <a name="cinternetfilewritestring"></a><a name="writestring"></a> CInternetFile:: WriteString

Bu işlev, ilişkili dosyaya null ile sonlandırılmış bir dize yazar.

```
virtual void WriteString(LPCTSTR pstr);
```

### <a name="parameters"></a>Parametreler

*PSTR*<br/>
Yazılacak içerikleri içeren bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Veriler yazılırken herhangi bir hata oluşursa, işlev hatayı açıklayan bir [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[CStdioFile sınıfı](../../mfc/reference/cstdiofile-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CInternetConnection sınıfı](../../mfc/reference/cinternetconnection-class.md)
