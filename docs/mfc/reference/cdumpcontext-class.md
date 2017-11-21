---
title: "CDumpContext sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords:
- CDumpContext [MFC], CDumpContext
- CDumpContext [MFC], DumpAsHex
- CDumpContext [MFC], Flush
- CDumpContext [MFC], GetDepth
- CDumpContext [MFC], HexDump
- CDumpContext [MFC], SetDepth
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fe45f47520efd0a96dff9b31f18eb267d0058c61
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdumpcontext-class"></a>CDumpContext sınıfı
Okunabilir metin biçiminde tanılama çıktıları akış odaklı destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDumpContext  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDumpContext::CDumpContext](#cdumpcontext)|Oluşturan bir `CDumpContext` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDumpContext::DumpAsHex](#dumpashex)|Belirtilen öğe onaltılık biçimde dökümünü yapar.|  
|[CDumpContext::Flush](#flush)|Döküm bağlamı arabelleğine herhangi bir veri aktarır.|  
|[CDumpContext::GetDepth](#getdepth)|Döküm derinliği karşılık gelen bir tamsayı alır.|  
|[CDumpContext::HexDump](#hexdump)|Bir dizi onaltılık biçimde bulunan bayt dökümünü yapar.|  
|[CDumpContext::SetDepth](#setdepth)|Döküm derinliğini ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDumpContext::operator&lt;&lt;](#operator_lt_lt)|Değişkenleri ve nesneleri döküm bağlamına ekler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CDumpContext`bir taban sınıfı yok.  
  
 Kullanabileceğiniz [afxDump](diagnostic-services.md#afxdump), bir predeclared `CDumpContext` , dökme çoğu için nesnesi. `afxDump` Nesne yalnızca Microsoft Foundation Class Kitaplığı hata ayıklama sürümü kullanılabilir.  
  
 Birkaç bellek [tanılama Hizmetleri](../../mfc/reference/diagnostic-services.md) kullanmak `afxDump` çıktılarını için.  
  
 Windows ortamı, önceden tanımlanmış çıkışı altında `afxDump` nesnesi, kavramsal olarak benzer şekilde `cerr` akışı, hata ayıklayıcı Windows işlevi aracılığıyla yönlendirilir **OutputDebugString**.  
  
 `CDumpContext` Sınıfına sahip aşırı yüklenmiş ekleme (  **<<** ) işleci için `CObject` nesnenin veri dökümleri işaretçileri. Türetilen bir nesne için bir özel döküm biçimi gerekiyorsa, geçersiz kılma [CObject::Dump](../../mfc/reference/cobject-class.md#dump). Çoğu Microsoft Foundation sınıf geçersiz kılınan bir uygulama `Dump` üye işlevi.  
  
 Öğesinden türetilmemiş sınıfları `CObject`, gibi `CString`, `CTime`, ve `CTimeSpan`, kendi aşırı yüklenmiş olan `CDumpContext` gibi sık kullanılan yapıları olarak ekleme işleçlerini **CFileStatus**, `CPoint`, ve `CRect`.  
  
 Kullanırsanız [ımplement_dynamıc](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) veya [ımplement_serıal](../../mfc/reference/run-time-object-model-services.md#implement_serial) sonra uygulamasında sınıfınızın makrosu `CObject::Dump` adını yazdırılır, `CObject`-türetilmiş sınıf. Aksi takdirde yazdırılır `CObject`.  
  
 `CDumpContext` Sınıf kitaplığı hata ayıklama ve yayın sürümleri ile kullanılabilir ancak `Dump` üye işlevi yalnızca hata ayıklama sürümü tanımlanır. Kullanım **#ifdef _DEBUG**  /  `#endif` özel dahil olmak üzere kodunuzu tanılama köşeli ayraç deyimleri `Dump` üye işlevleri.  
  
 Kendi oluşturmadan önce `CDumpContext` nesnesi oluşturmanız gerekir bir `CFile` döküm hedef olarak hizmet veren nesne.  
  
 Daha fazla bilgi için `CDumpContext`, bkz: [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques).  
  
 **# _DEBUG define**  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CDumpContext`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="cdumpcontext"></a>CDumpContext::CDumpContext  
 Sınıfın bir nesnesi oluşturur `CDumpContext`.  
  
```  
CDumpContext(CFile* pFile = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFile`  
 Bir işaretçi `CFile` döküm hedef nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 `afxDump` Nesne otomatik olarak oluşturulur.  
  
 Arka plandaki için yazma `CFile` döküm bağlam olmakla birlikte etkin; Aksi takdirde, döküm ile çalışmasını engeller. Windows ortamı altında çıkış hata ayıklayıcı Windows işlevi aracılığıyla yönlendirilir **OutputDebugString**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]  
  
##  <a name="dumpashex"></a>CDumpContext::DumpAsHex  
 Onaltılık sayı olarak biçimlendirilmiş belirtilen tür dökümünü yapar.  
  
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
 Bir başvuru bir `CDumpContext` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğesi belirtilen türde bir onaltılık sayı olarak dökümü bu üye işlevini çağırın. Bir dizi dökümü çağrısı [CDumpContext::HexDump](#hexdump).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]  
  
##  <a name="flush"></a>CDumpContext::Flush  
 Zorlar dosyasına yazılacak arabellekleri kalan herhangi bir veri dökümü bağlamına bağlı.  
  
```  
void Flush();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]  
  
##  <a name="getdepth"></a>CDumpContext::GetDepth  
 Derin veya basit bir döküm işleminde olup olmadığını belirler.  
  
```  
int GetDepth() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirlenen döküm derinliği `SetDepth`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [SetDepth](#setdepth).  
  
##  <a name="hexdump"></a>CDumpContext::HexDump  
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
 Yeni bir satır başlangıcında çıktısını almak için bir dize.  
  
 *pby*  
 Döküm baytları içeren bir arabellek için bir işaretçi.  
  
 `nBytes`  
 Döküm bayt sayısı.  
  
 `nWidth`  
 En fazla bayt sayısı (çıktı çizginin genişliğini değil) satır yazılan.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir tek, belirli öğesi türü bir onaltılık sayı olarak dökümü çağrısı [CDumpContext::DumpAsHex](#dumpashex).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]  
  
##  <a name="operator_lt_lt"></a>CDumpContext::operator&lt;&lt;  
 Döküm bağlamı için belirtilen veri çıkarır.  
  
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
 A `CDumpContext` başvuru. Dönüş değerini kullanarak, kaynak kodu tek bir satıra birden çok eklemeleri yazabilirsiniz.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin ekleme işleci aşırı `CObject` en basit türler için de işaretçileri. Bir işaretçi bir döküm sonuçlanır karakter dizesi İçindekiler; bir işaretçi `void` sonuçları adresi yalnızca içinde bir onaltılık dökümü. A **LONGLONG** sonuçları bir 64-bit işaretli tamsayıyı; bir dökümünü A **ULONGLONG** bir 64-bit işaretsiz tamsayıyı bir dökümünü neden olur.  
  
 Kullanırsanız `IMPLEMENT_DYNAMIC` veya `IMPLEMENT_SERIAL` makrosu sınıfınız, daha sonra ekleme işleci uygulamasında aracılığıyla `CObject::Dump`, adını yazdırılır, `CObject`-türetilmiş sınıf. Aksi takdirde yazdırılır `CObject`. Geçersiz kılarsanız `Dump` sınıfı, daha sonra işlev, nesnenin içeriğini bir onaltılık dökümü yerine daha anlamlı çıktısını sağlayabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]  
  
##  <a name="setdepth"></a>CDumpContext::SetDepth  
 Döküm derinliği ayarlar.  
  
```  
void SetDepth(int nNewDepth);
```  
  
### <a name="parameters"></a>Parametreler  
 *nNewDepth*  
 Yeni derinliği değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 İlkel tür veya basit dökme durumunda `CObject` diğer nesnelere hiçbir işaretçileri içeren sonra 0 değeri yeterlidir. 0 tüm nesneler olduğu derin bir döküm belirtilenden daha büyük bir değer yinelemeli olarak yazılan. Örneğin, bir koleksiyon, derin bir dökümü koleksiyonunun tüm öğeleri döküm. Türetilmiş sınıflarda diğer belirli derinliği değerleri kullanabilirsiniz.  
  
> [!NOTE]
>  Döngüsel başvuru içinde derin dökümleri algılanmaz ve sonsuz Döngülerde neden olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CFile sınıfı](../../mfc/reference/cfile-class.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)
