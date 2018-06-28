---
title: CInternetFile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c60027195024a9abb1af5ce5ec47dc6f6a6bfbf8
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038991"
---
# <a name="cinternetfile-class"></a>CInternetFile sınıfı
Internet protokolleri kullanır uzak sistemlere dosyalara erişim sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CInternetFile : public CStdioFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInternetFile::CInternetFile](#cinternetfile)|Oluşturan bir `CInternetFile` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInternetFile::Abort](#abort)|Tüm uyarıları ve hataları yoksayma dosyanın kapatır.|  
|[CInternetFile::Close](#close)|Kapatan bir `CInternetFile` ve kaynaklarını serbest bırakır.|  
|[CInternetFile::Flush](#flush)|Yazma arabelleğini içeriği aktarır ve bellek verileri hedef makineye yazılır emin olur.|  
|[CInternetFile::GetLength](#getlength)|Dosyanın boyutu döndürür.|  
|[CInternetFile::Read](#read)|Belirtilen bayt sayısını okur.|  
|[CInternetFile::ReadString](#readstring)|Karakter akışı okur.|  
|[CInternetFile::Seek](#seek)|İşaretçi açık bir dosyayı yeniden konumlandırır.|  
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|Arabellek boyutu, veri okuma burada ayarlar.|  
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|Arabellek boyutu, veri yazılacağı ayarlar.|  
|[CInternetFile::Write](#write)|Belirtilen bayt sayısı yazar.|  
|[CInternetFile::WriteString](#writestring)|Sonlandırılmış bir dize bir dosyaya yazar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInternetFile::operator HINTERNET](#operator_hinternet)|Bir Internet işlemesi için bir atama işleci.|  
  
### <a name="protected-data-members"></a>Korumalı veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInternetFile::m_hFile](#m_hfile)|Bir dosya için bir tanıtıcı.|  
  
## <a name="remarks"></a>Açıklamalar  
 İçin temel sınıf sağlar [CHttpFile](../../mfc/reference/chttpfile-class.md) ve [CGopherFile](../../mfc/reference/cgopherfile-class.md) dosya sınıfları. Hiçbir zaman oluşturduğunuz bir `CInternetFile` doğrudan nesne. Bunun yerine, çağırarak türetilmiş sınıflarından biri bir nesne oluşturma [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) veya [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Ayrıca bir `CInternetFile` çağırarak nesne [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
 `CInternetFile` Üye işlevleri `Open`, `LockRange`, `UnlockRange`, ve `Duplicate` için uygulanmadı `CInternetFile`. Bu işlevler çağırırsanız bir `CInternetFile` nesne alırsınız bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Hakkında daha fazla bilgi için `CInternetFile` diğer MFC Internet sınıfları ile works başlıklı makaleye bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="abort"></a>  CInternetFile::Abort  
 Bu nesneyle ilişkili dosyayı kapatır ve dosyayı okuma veya yazma için kullanılabilir hale getirir.  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya nesnesi yok etme önce kapatılmamış, yıkıcı sizin için kapatılır.  
  
 Özel durumlar, işlerken `Abort` farklıdır [Kapat](#close) iki önemli şekilde. İlk olarak, `Abort` işlevi değil throw bir özel durum hatalarında hataları yoksayar çünkü. İkinci, `Abort` yok **ASSERT** dosya açılmamış olan veya daha önce kapatıldı.  
  
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
 *Hfıle*  
 Internet dosyası için bir tanıtıcı.  
  
 *pstrFileName*  
 Dosya adı içeren bir dize için bir işaretçi.  
  
 *pConnection*  
 Bir işaretçi bir [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) nesnesi.  
  
 *bReadMode*  
 Dosyanın salt okunur olup olmadığını gösterir.  
  
 *hSession*  
 Bir Internet oturumu için bir tanıtıcı.  
  
 *pstrServer*  
 Sunucu adını içeren bir dize için bir işaretçi.  
  
 *dwContext*  
 İçerik tanımlayıcısını `CInternetFile` nesnesi. Bkz: [WinINet Temelleri](../../mfc/wininet-basics.md) bağlamı tanımlayıcısı hakkında daha fazla bilgi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir zaman oluşturduğunuz bir `CInternetFile` doğrudan nesne. Bunun yerine, çağırarak türetilmiş sınıflarından biri bir nesne oluşturma [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) veya [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Ayrıca bir `CInternetFile` çağırarak nesne [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
##  <a name="close"></a>  CInternetFile::Close  
 Kapatan bir `CInternetFile` ve tüm kaynaklarını serbest bırakır.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dosya yazma için açılmış, bir örtük çağrısına yoktur [Flush](#flush) tüm veri arabelleğe güvence altına almak için ana bilgisayara yazılır. Çağırmalısınız **Kapat** bir dosyayı kullanarak bittiğinde.  
  
##  <a name="flush"></a>  CInternetFile::Flush  
 Yazma arabelleğini içeriğini temizlemek için bu üye işlevini çağırın.  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `Flush` bellekteki tüm verileri gerçekten yazıldı, hedef makine güvence altına almak için ve işleminizin ana makineyle tamamlanmış güvence altına almak için. `Flush` Yalnızca üzerinde etkili olan `CInternetFile` nesneleri yazma için açılmış.  
  
##  <a name="getlength"></a>  CInternetFile::GetLength  
 Dosyanın boyutu döndürür.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
##  <a name="m_hfile"></a>  CInternetFile::m_hFile  
 Bu nesneyle ilişkili dosya için bir tanıtıcı.  
  
```  
HINTERNET m_hFile;  
```  
  
##  <a name="operator_hinternet"></a>  CInternetFile::operator HINTERNET  
 Windows tanıtıcı geçerli Internet oturumu için almak için bu işleci kullanın.  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="read"></a>  CInternetFile::Read  
 Verilen belleğe başlayarak okumak için bu üye işlev çağrısı *lpvBuf*, bayt sayısı belirtilen *nCount*.  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpBuf*  
 Hangi dosya veri okunurken bir bellek adresi için bir işaretçi.  
  
 *nCount*  
 Yazılacak bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arabelleğe aktarılan toplam bayt sayısı. Dönüş değeri olabilir değerinden *nCount* varsa dosya sonuna ulaşıldı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevi gerçekte okunan bayt sayısını verir — olabilir bir sayı değerinden *nCount* dosya biterse. Dosyası okunurken bir hata meydana gelirse, işlev oluşturur bir [CInternetException](../../mfc/reference/cinternetexception-class.md) hatayı açıklayan nesne. Okuma dosyanın sonunu aşan bir hata olarak kabul edilmez ve hiçbir özel durum unutmayın.  
  
 Tüm verileri alındığından emin olmak için bir uygulama çağırmak devam etmeniz gerekir **CInternetFile::Read** yöntemi sıfır dönene kadar yöntemi.  
  
##  <a name="readstring"></a>  CInternetFile::ReadString  
 Yeni satır karakteri bulana kadar karakter akışı okumak için bu üye işlevini çağırın.  
  
```  
virtual BOOL ReadString(CString& rString);

 
virtual LPTSTR ReadString(
    LPTSTR pstr,  
    UINT nMax);
```  
  
### <a name="parameters"></a>Parametreler  
 *pstr*  
 Okunan satır alacak bir dize için bir işaretçi.  
  
 *nMax*  
 Okunacak karakter sayısı.  
  
 *rString*  
 Bir başvuru [CString](../../atl-mfc-shared/reference/cstringt-class.md) okuma satırın alan nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi hizmetinden alınan düz verileri içeren arabellek [CInternetFile](../../mfc/reference/cinternetfile-class.md) nesnesi. Bu yönteme geçirilen arabellek veri türü, bağımsız olarak, tüm işlemeleri verileri (örneğin, Unicode dönüştürme) gerçekleştirmez, döndürülen veri yapısına eşlemeniz gerekir böylece beklediğiniz gibi **void\***  bir tür döndürdü.  
  
 **NULL** dosya sonu herhangi bir veri; okumadan ulaştıysanız veya boolean ise, **FALSE** dosya sonu herhangi bir veri okumadan ulaştıysanız.  
  
### <a name="remarks"></a>Açıklamalar  
 Sonuçta elde edilen satır işlevi tarafından başvurulan bellek yerleştirir *pstr* parametresi. Karakterleri okuma durdurur tarafından belirtilen karakter üst sınırını ulaştığında *nMax*. Arabellek her zaman bir sonlandırma null karakteri alır.  
  
 Çağırırsanız `ReadString` ilk çağırmadan [SetReadBufferSize](#setreadbuffersize), 4096 bayt arabellek alırsınız.  
  
##  <a name="seek"></a>  CInternetFile::Seek  
 İşaretçinin daha önce açılmış bir dosyada yeniden konumlandırmak için bu üye işlevini çağırın.  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOffset,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>Parametreler  
 *lOffset*  
 Dosya okuma/yazma işaretçiyi taşımak için bayt cinsinden uzaklık.  
  
 *nFrom*  
 Uzaklık göreli referansı. Aşağıdaki değerlerden biri olmalıdır:  
  
- **CFile::begin** dosya işaretçisini *lOff* bayt iletmek dosya baştan.  
  
- **CFile::current** dosya işaretçisini *lOff* dosyayı geçerli konumundan bayt.  
  
- **CFile::end** dosya işaretçisini *lOff* dosyasının sonuna baytlar. *lOff* gerekir olması mevcut arama negatif dosya; değerleri arama için dosya sonunun pozitif.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İstenen konumu yasal ise dosya başından uzaklık yeni bayt; Aksi takdirde, değerler tanımsızdır ve [CInternetException](../../mfc/reference/cinternetexception-class.md) nesnesi oluşturulur.  
  
### <a name="remarks"></a>Açıklamalar  
 `Seek` İşlevi izin verir. bir dosyanın içeriğini için rasgele erişim işaretçiyi taşıyarak belirtilen tutarı, mutlak veya göreli olarak. Hiçbir veri gerçekte arama sırasında okuyun.  
  
 Şu anda bu üye işlevine bir çağrı yalnızca ilişkilendirilmiş verileri için desteklenen `CHttpFile` nesneleri. FTP veya gopher istekleri için desteklenmez. Çağırırsanız `Seek` desteklenmeyen Bu hizmetlerden biri için geri, Win32 hata kodu geçer **ERROR_INTERNET_INVALID_OPERATION**.  
  
 Bir dosya açıldığında dosya işaretçisini uzaklığı 0, dosyasının başında ' dir.  
  
> [!NOTE]
>  Kullanarak `Seek` örtük bir çağrı neden olabilecek [Flush](#flush).  
  
### <a name="example"></a>Örnek  
  Taban sınıfı uygulama örneğin bakın ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek)).  
  
##  <a name="setreadbuffersize"></a>  CInternetFile::SetReadBufferSize  
 Tarafından kullanılan geçici okuma arabelleğinin boyutunu ayarlamak için bu üye işlevini çağırın bir `CInternetFile`-türetilmiş bir nesne içermelidir.  
  
```  
BOOL SetReadBufferSize(UINT nReadSize);
```  
  
### <a name="parameters"></a>Parametreler  
 *nReadSize*  
 Bayt cinsinden istenen arabellek boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel alınan WinINet API'leri değil arabelleğe alma gerçekleştirmek, bu nedenle verileri okumak için veri miktarını bağımsız olarak verimli bir şekilde okumak uygulamanızı sağlayan bir arabellek boyutu seçin. Her için çağırırsanız [okuma](#read) normalde büyük aount içerir (örneğin, dört veya daha fazla kilobayt) verileri bir arabellek gerekmemelidir. Ancak, çağırırsanız `Read` küçük parçalara veri almak için veya kullanıyorsanız [ReadString'i](#readstring) Okuma arabelleği uygulama performansını artıran sonra tek tek satırların aynı anda okunamıyor.  
  
 Varsayılan olarak, bir `CInternetFile` nesne için Okuma arabelleği sağlamaz. Bu üye işlevini çağırırsanız, dosya için okuma erişimi açılmış emin olmalısınız.  
  
 Herhangi bir zamanda arabellek boyutunu artırabilir, ancak arabellek küçültme hiçbir etkisi olmaz. Çağırırsanız [ReadString'i](#readstring) ilk çağırmadan `SetReadBufferSize`, 4096 bayt arabellek alırsınız.  
  
##  <a name="setwritebuffersize"></a>  CInternetFile::SetWriteBufferSize  
 Tarafından kullanılan geçici yazma arabelleği boyutunu ayarlamak için bu üye işlevini çağırın bir `CInternetFile`-türetilmiş bir nesne içermelidir.  
  
```  
BOOL SetWriteBufferSize(UINT nWriteSize);
```  
  
### <a name="parameters"></a>Parametreler  
 *nWriteSize*  
 Arabelleğinin bayt cinsinden boyutu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 WinINet API'leri yok gerçekleştirmek arabelleğe alma, arka plandaki verimli bir şekilde yazılacak veri miktarını bağımsız olarak veri yazmak uygulamanızı sağlayan bir arabellek boyutu için seçin. Her için çağırırsanız [yazma](#write) normalde büyük bir miktarını içerir (örneğin, dört veya daha fazla kilobayt birer birer) verileri bir arabellek gerekmemelidir. Ancak, çağırırsanız [yazma](#write) küçük parçalara veri yazmak için bir yazma arabelleği, uygulamanızın performansını artırır.  
  
 Varsayılan olarak, bir `CInternetFile` nesne yazmak için arabelleğe sağlamaz. Bu üye işlevini çağırırsanız, dosya yazma erişimi için açıldı emin olmalısınız. Yazma arabelleği boyutu dilediğiniz zaman değiştirebilirsiniz, ancak bunun nedenle örtük bir çağrı neden olur [Flush](#flush).  
  
##  <a name="write"></a>  CInternetFile::Write  
 Verilen belleğe yazmak için bu üye işlevini çağırın *lpvBuf*, bayt sayısı belirtilen *nCount*.  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpBuf*  
 Bir işaretçi yazılması için ilk bayta.  
  
 *nCount*  
 Yazılacak bayt sayısını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Veriler yazılırken herhangi bir hata meydana gelirse, işlev oluşturur bir [CInternetException](../../mfc/reference/cinternetexception-class.md) hatayı açıklayan nesne.  
  
##  <a name="writestring"></a>  CInternetFile::WriteString  
 Bu işlev null ile sonlandırılmış bir dize ilişkili dosyasına yazar.  
  
```  
virtual void WriteString(LPCTSTR pstr);
```  
  
### <a name="parameters"></a>Parametreler  
 *pstr*  
 Yazılacak içeriği içeren bir dize için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Veriler yazılırken herhangi bir hata meydana gelirse, işlev oluşturur bir [CInternetException](../../mfc/reference/cinternetexception-class.md) hatayı açıklayan nesne.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CStdioFile sınıfı](../../mfc/reference/cstdiofile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CInternetConnection Sınıfı](../../mfc/reference/cinternetconnection-class.md)
