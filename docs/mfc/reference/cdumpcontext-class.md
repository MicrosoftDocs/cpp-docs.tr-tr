---
title: CDumpContext sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDumpContext
- AFX/CDumpContext
- AFX/CDumpContext::CDumpContext
- AFX/CDumpContext::DumpAsHex
- AFX/CDumpContext::Flush
- AFX/CDumpContext::GetDepth
- AFX/CDumpContext::HexDump
- AFX/CDumpContext::SetDepth
dev_langs:
- C++
helpviewer_keywords:
- CDumpContext [MFC], CDumpContext
- CDumpContext [MFC], DumpAsHex
- CDumpContext [MFC], Flush
- CDumpContext [MFC], GetDepth
- CDumpContext [MFC], HexDump
- CDumpContext [MFC], SetDepth
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d80ed097056c9d52f5f9d98ab8e3f80fae431d98
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336351"
---
# <a name="cdumpcontext-class"></a>CDumpContext sınıfı
Tanı çıktısını insanlar tarafından okunabilen metin biçiminde akış temelli destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDumpContext  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDumpContext::CDumpContext](#cdumpcontext)|Oluşturur bir `CDumpContext` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDumpContext::DumpAsHex](#dumpashex)|Belirtilen öğe on altılık biçimde dökümlerini.|  
|[CDumpContext::Flush](#flush)|Döküm bağlamı arabelleğinde tüm verileri temizler.|  
|[CDumpContext::GetDepth](#getdepth)|Döküm derinliğini karşılık gelen bir tamsayı olarak alır.|  
|[CDumpContext::HexDump](#hexdump)|Onaltılık biçimde bir dizi içindeki bayt dökümünü yapar.|  
|[CDumpContext::SetDepth](#setdepth)|Döküm derinliğini ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDumpContext::operator &lt;&lt;](#operator_lt_lt)|Değişkenler ve nesneler döküm bağlamına ekler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDumpContext` bir temel sınıfa sahip değil.  
  
 Kullanabileceğiniz [afxDump](diagnostic-services.md#afxdump), bir önceden bildirilen `CDumpContext` dökme, çoğu için bir nesne. `afxDump` Nesne yalnızca Microsoft Foundation Class Kitaplığı hata ayıklama sürümü kullanılabilir.  
  
 Bazı bellek [tanı Hizmetleri](../../mfc/reference/diagnostic-services.md) kullanın `afxDump` çıktılarını için.  
  
 Önceden tanımlanmış çıktısı Windows ortamını altında `afxDump` nesne, kavramsal olarak benzer şekilde `cerr` akışı, hata ayıklayıcı Windows işlev aracılığıyla yönlendirilir `OutputDebugString`.  
  
 `CDumpContext` Sınıfında aşırı yüklenmiş bir ekleme ( **<<**) için işleç `CObject` işaretçileri, nesne verilerinin dökümünü yapar. Türetilen bir nesne için bir özel döküm biçiminde gerekiyorsa, geçersiz kılma [CObject::Dump](../../mfc/reference/cobject-class.md#dump). Çoğu Microsoft Foundation sınıfları geçersiz kılınan bir uygulama `Dump` üye işlevi.  
  
 Türetilmiş değil sınıfları `CObject`, gibi `CString`, `CTime`, ve `CTimeSpan`, kendi aşırı yüklenmiş olan `CDumpContext` gibi sık kullanılan yapıları olarak ekleme işleçlerini `CFileStatus`, `CPoint`, ve `CRect`.  
  
 Kullanırsanız [ımplement_dynamıc](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) veya [ımplement_serıal](../../mfc/reference/run-time-object-model-services.md#implement_serial) ardından uygulamasında sınıfınızın makrosu `CObject::Dump` adını yazdırılır, `CObject`-türetilmiş sınıf. Aksi takdirde, yazdırılacağı `CObject`.  
  
 `CDumpContext` Sınıf kitaplığı hata ayıklama ve yayın sürümleri ile kullanılabilir ancak `Dump` üye işlevi, yalnızca hata ayıklama sürümünde tanımlanır. Kullanım **#ifdef _DEBUG**  /  `#endif` deyimlerini içeren kendi özel kodunuzu tanılama köşeli ayraç `Dump` üye işlevleri.  
  
 Kendi oluşturmadan önce `CDumpContext` nesnesi oluşturmanız gerekir bir `CFile` döküm hedef olarak hizmet veren nesne.  
  
 Daha fazla bilgi için `CDumpContext`, bkz: [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques).  
  
 **#define _DEBUG**  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CDumpContext`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="cdumpcontext"></a>  CDumpContext::CDumpContext  
 Sınıfın bir nesnesi oluşturur `CDumpContext`.  
  
```  
CDumpContext(CFile* pFile = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *pFile*  
 Bir işaretçi `CFile` döküm hedef nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `afxDump` Nesne otomatik olarak oluşturulur.  
  
 Temel alınan yazma `CFile` döküm içeriği olmakla birlikte etkin; Aksi takdirde, döküm ile çalışmasını engeller. Windows ortamı çıkış hata ayıklayıcı Windows işlev aracılığıyla yönlendirilir `OutputDebugString`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]  
  
##  <a name="dumpashex"></a>  CDumpContext::DumpAsHex  
 Belirtilen tür onaltılık sayı olarak biçimlendirilmiş dökümünü yapar.  
  
```  
CDumpContext& DumpAsHex(BYTE b);  
CDumpContext& DumpAsHex(DWORD dw);  
CDumpContext& DumpAsHex(int n);  
CDumpContext& DumpAsHex(LONG l);  
CDumpContext& DumpAsHex(LONGLONG n);  
CDumpContext& DumpAsHex(UINT u);  
CDumpContext& DumpAsHex(ULONGLONG n);  
CDumpContext& DumpAsHex(WORD w);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru bir `CDumpContext` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğesi belirtilen türde bir onaltılık sayı olarak dökümünü almak için bu üye işlevini çağırın. Bir dizi dökümünü almak için çağrı [CDumpContext::HexDump](#hexdump).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]  
  
##  <a name="flush"></a>  CDumpContext::Flush  
 Zorlar dosyaya yazılacak arabellek içinde kalan herhangi bir veri döküm bağlamına iliştirilemez.  
  
```  
void Flush();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]  
  
##  <a name="getdepth"></a>  CDumpContext::GetDepth  
 Derin veya yüzeysel bir döküm işleminde olup olmadığını belirler.  
  
```  
int GetDepth() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döküm tarafından belirlenen derinliğini `SetDepth`.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [SetDepth](#setdepth).  
  
##  <a name="hexdump"></a>  CDumpContext::HexDump  
 Onaltılık sayı olarak biçimlendirilmiş bir bayt dizisi dökümünü yapar.  
  
```  
void HexDump(
    LPCTSTR lpszLine,  
    BYTE* pby,  
    int nBytes,  
    int nWidth);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszLine*  
 Yeni bir satır başında çıktısını almak için bir dize.  
  
 *pby*  
 Döküm baytları içeren arabellek için işaretçi.  
  
 *nBytes*  
 Dökümü alınacak bayt sayısı.  
  
 *nWidth*  
 En büyük bayt sayısını (çıkış çizginin genişliğini değil) satır yazılan.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tek, belirli bir öğe türü bir onaltılık sayı olarak dökümünü almak için çağrı [CDumpContext::DumpAsHex](#dumpashex).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]  
  
##  <a name="operator_lt_lt"></a>  CDumpContext::operator &lt;&lt;  
 Döküm bağlam belirtilen verileri çıkarır.  
  
```  
CDumpContext& operator<<(const CObject* pOb);  
CDumpContext& operator<<(const CObject& ob);  
CDumpContext& operator<<(LPCTSTR lpsz);  
CDumpContext& operator<<(const void* lp);  
CDumpContext& operator<<(BYTE by);  
CDumpContext& operator<<(WORD w);  
CDumpContext& operator<<(DWORD dw);  
CDumpContext& operator<<(int n);  
CDumpContext& operator<<(double d);  
CDumpContext& operator<<(float f);  
CDumpContext& operator<<(LONG l);  
CDumpContext& operator<<(UINT u);  
CDumpContext& operator<<(LPCWSTR lpsz);  
CDumpContext& operator<<(LPCSTR lpsz);  
CDumpContext& operator<<(LONGLONG n);  
CDumpContext& operator<<(ULONGLONG n);  
CDumpContext& operator<<(HWND h);  
CDumpContext& operator<<(HDC h);  
CDumpContext& operator<<(HMENU h);  
CDumpContext& operator<<(HACCEL h);  
CDumpContext& operator<<(HFONT h);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CDumpContext` başvuru. Dönüş değeri kullanarak, kaynak kodunu tek bir satıra birden çok eklemeler yazabilirsiniz.  
  
### <a name="remarks"></a>Açıklamalar  
 Ekleme işleci için aşırı yüklenmiş `CObject` işaretçileri de en temel türlerin sunamıyoruz. Dize içeriklerini dökümü içinde karaktere bir işaretçi sonuçlanır; bir işaretçi **void** adresinin yalnızca onaltılık bir döküm sonuçlanır. Bir 64-bit imzalı bir tamsayı dökümü içinde bir LONGLONG sonuçlanır; Bir 64-bit işaretsiz tamsayıyı dökümü içinde bir ULONGLONG sonuçlanır.  
  
 Sınıfınız, daha sonra ekleme işleci, uygulamada ımplement_dynamıc veya ımplement_serıal makrosu aracılığıyla kullanırsanız `CObject::Dump`, adı yazdırır, `CObject`-türetilmiş sınıf. Aksi takdirde, yazdırılacağı `CObject`. Kılarsanız `Dump` sınıfı, daha sonra işlev nesnesinin içindekiler onaltılık bir döküm yerine daha anlamlı bir çıkış sağlayabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]  
  
##  <a name="setdepth"></a>  CDumpContext::SetDepth  
 Derinlik döküm için ayarlar.  
  
```  
void SetDepth(int nNewDepth);
```  
  
### <a name="parameters"></a>Parametreler  
 *nNewDepth*  
 Yeni derinliği değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir basit tür veya basit dökme varsa `CObject` hiçbir diğer nesnelerine işaretçiler içeren, ardından 0 değerini yeterlidir. 0 tüm nesneler olduğu ayrıntılı bir dökümü belirtilenden daha büyük bir değere yinelemeli olarak yazılan. Örneğin, bir koleksiyonun ayrıntılı bir dökümü tüm koleksiyon öğelerini döküm. Diğer belirli derinliği değerleri, türetilmiş sınıflarda kullanabilir.  
  
> [!NOTE]
>  Döngüsel başvurular derin dökümlerde algılanmayan ve sonsuz döngüler neden olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFile sınıfı](../../mfc/reference/cfile-class.md)   
 [CObject Sınıfı](../../mfc/reference/cobject-class.md)
