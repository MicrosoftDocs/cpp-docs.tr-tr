---
title: CDumpContext sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDumpContext
- AFX/CDumpContext
- AFX/CDumpContext::CDumpContext
- AFX/CDumpContext::DumpAsHex
- AFX/CDumpContext::Flush
- AFX/CDumpContext::GetDepth
- AFX/CDumpContext::HexDump
- AFX/CDumpContext::SetDepth
helpviewer_keywords:
- CDumpContext [MFC], CDumpContext
- CDumpContext [MFC], DumpAsHex
- CDumpContext [MFC], Flush
- CDumpContext [MFC], GetDepth
- CDumpContext [MFC], HexDump
- CDumpContext [MFC], SetDepth
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
ms.openlocfilehash: 3a81e06586e6de14d57ce4c4de36dc30c73383f1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212520"
---
# <a name="cdumpcontext-class"></a>CDumpContext sınıfı

, İnsan tarafından okunabilen metin biçiminde akış odaklı tanılama çıkışını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CDumpContext
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDumpContext:: CDumpContext](#cdumpcontext)|Bir `CDumpContext` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDumpContext::D umpAsHex](#dumpashex)|Belirtilen öğeyi onaltılık biçimde döker.|
|[CDumpContext:: Flush](#flush)|Döküm bağlamı arabelleğindeki tüm verileri temizler.|
|[CDumpContext:: GetDepth](#getdepth)|Döküm derinliğine karşılık gelen bir tamsayı alır.|
|[CDumpContext:: Onaltıkdöküm](#hexdump)|Bir dizide bulunan baytları onaltılık biçimde döker.|
|[CDumpContext:: SetDepth](#setdepth)|Döküm derinliğini ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CDumpContext:: işleci&lt;&lt;](#operator_lt_lt)|Döküm bağlamına değişkenler ve nesneler ekler.|

## <a name="remarks"></a>Açıklamalar

`CDumpContext`taban sınıfına sahip değildir.

Dökümüden büyük bir olasılıkla, önceden tanımlanmış bir nesne olan [afxDump](diagnostic-services.md#afxdump)'ı kullanabilirsiniz `CDumpContext` . `afxDump`Nesne yalnızca Microsoft Foundation Class Kitaplığı hata ayıklama sürümünde kullanılabilir.

Birçok bellek [Tanılama Hizmeti](../../mfc/reference/diagnostic-services.md) `afxDump` çıkışı için kullanılır.

Windows ortamı altında, kavramsal olarak akışa benzeyen önceden tanımlanmış `afxDump` nesnenin çıktısı `cerr` , Windows işlevi aracılığıyla hata ayıklayıcıya yönlendirilir `OutputDebugString` .

`CDumpContext`Sınıfında, **<<** `CObject` nesne verilerinin dökümünü yapan işaretçiler için aşırı yüklenmiş bir ekleme () işleci vardır. Türetilmiş bir nesne için özel bir döküm biçimine ihtiyacınız varsa, [CObject::D UMP](../../mfc/reference/cobject-class.md#dump)öğesini geçersiz kılın. Çoğu Microsoft Foundation sınıfı geçersiz kılınan bir `Dump` üye işlevi uygular.

, Ve gibi öğesinden türetilmeyen sınıfların,, `CObject` `CString` ve gibi `CTime` `CTimeSpan` `CDumpContext` sık kullanılan ekleme işleçleri vardır `CFileStatus` `CPoint` `CRect` .

Sınıfınızın uygulamasında [IMPLEMENT_DYNAMIC](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) veya [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) makrosunu kullanırsanız, `CObject::Dump` türetilmiş sınıfınızın adını yazdıracaksınız `CObject` . Aksi takdirde, yazdırılır `CObject` .

`CDumpContext`Sınıfı, kitaplığın hata ayıklama ve yayın sürümleriyle kullanılabilir, ancak `Dump` üye Işlevi yalnızca hata ayıklama sürümünde tanımlanmıştır. **#ifdef _DEBUG**  /  `#endif` Özel üye işlevleriniz de dahil olmak üzere tanılama kodunuzu parantez içine almak için #ifdef _debug deyimlerini kullanın `Dump` .

Kendi nesneniz oluşturmadan önce `CDumpContext` , `CFile` döküm hedefi görevi gören bir nesne oluşturmanız gerekir.

Hakkında daha fazla bilgi için `CDumpContext` bkz. [MFC uygulamalarında hata ayıklama](/visualstudio/debugger/mfc-debugging-techniques).

**#define _DEBUG**

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDumpContext`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="cdumpcontextcdumpcontext"></a><a name="cdumpcontext"></a>CDumpContext:: CDumpContext

Sınıfının bir nesnesini oluşturur `CDumpContext` .

```
CDumpContext(CFile* pFile = NULL);
```

### <a name="parameters"></a>Parametreler

*pFile*<br/>
`CFile`Döküm hedefi olan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`afxDump`Nesne otomatik olarak oluşturulur.

Döküm bağlamı etkinken temel içine yazma `CFile` ; Aksi takdirde, döküm ile karışacaktır. Windows ortamı altında, çıkış hata ayıklayıcıya Windows işlevi aracılığıyla yönlendirilir `OutputDebugString` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]

## <a name="cdumpcontextdumpashex"></a><a name="dumpashex"></a>CDumpContext::D umpAsHex

Belirtilen türü onaltılık sayı olarak biçimlendirilen şekilde döker.

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

Bir `CDumpContext` nesneye başvuru.

### <a name="remarks"></a>Açıklamalar

Belirtilen türdeki öğenin bir onaltılık sayı olarak dökümünü almak için bu üye işlevi çağırın. Bir dizinin dökümünü yapmak için [CDumpContext:: Onaltıal dökümünü](#hexdump)çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]

## <a name="cdumpcontextflush"></a><a name="flush"></a>CDumpContext:: Flush

Arabelleklerden kalan tüm verileri, döküm bağlamına eklenen dosyaya yazılacak şekilde zorlar.

```cpp
void Flush();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]

## <a name="cdumpcontextgetdepth"></a><a name="getdepth"></a>CDumpContext:: GetDepth

Derin veya basit bir dökümün işlem içinde olup olmadığını belirler.

```
int GetDepth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Döküm tarafından ayarlandığı şekilde döküm derinliği `SetDepth` .

### <a name="example"></a>Örnek

  [SetDepth](#setdepth)örneğine bakın.

## <a name="cdumpcontexthexdump"></a><a name="hexdump"></a>CDumpContext:: Onaltıkdöküm

Onaltılık sayı olarak biçimlendirilen bir bayt dizisinin dökümünü yapar.

```cpp
void HexDump(
    LPCTSTR lpszLine,
    BYTE* pby,
    int nBytes,
    int nWidth);
```

### <a name="parameters"></a>Parametreler

*lpszLine*<br/>
Yeni bir satırın başlangıcında çıktının çıktısını almak için bir dize.

*PBY*<br/>
Dökümünü almak için bayt içeren bir arabelleğin işaretçisi.

*nBytes*<br/>
Döküm edilecek bayt sayısı.

*nWidth*<br/>
Satır başına alınan bayt sayısı üst sınırı (çıkış çizgisinin genişliği değil).

### <a name="remarks"></a>Açıklamalar

Tek, belirli bir öğe türünün onaltılık sayı olarak dökümünü yapmak için, [CDumpContext::D umpAsHex](#dumpashex)öğesini çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]

## <a name="cdumpcontextoperator-ltlt"></a><a name="operator_lt_lt"></a>CDumpContext:: işleci&lt;&lt;

Belirtilen verileri döküm bağlamına verir.

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

Bir `CDumpContext` başvuru. Dönüş değerini kullanarak, tek bir kaynak kodu satırına birden fazla ekleme yazabilirsiniz.

### <a name="remarks"></a>Açıklamalar

Ekleme işleci, `CObject` işaretçiler ve çoğu basit tür için aşırı yüklenmiştir. Karakter işaretçisi, dize içeriklerinin dökümünde oluşur; **`void`** yalnızca adresin onaltılı dökümünü elde eden bir işaretçi. Bir 64 bitlik işaretli tamsayının dökümünde LONGLONG oluşur; Bir ULONGLONG, 64 bitlik işaretsiz bir tamsayı dökümünü elde ediyor.

Sınıfınızın uygulamasında IMPLEMENT_DYNAMIC veya IMPLEMENT_SERIAL makrosunu kullanırsanız, içindeki ekleme işleci, `CObject::Dump` türetilmiş sınıfınızın adını yazdıracaktır `CObject` . Aksi takdirde, yazdırılır `CObject` . Sınıfının işlevini geçersiz kılarsınız `Dump` , onaltılık döküm yerine nesnenin içeriklerinin daha anlamlı bir çıktısını sağlayabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]

## <a name="cdumpcontextsetdepth"></a><a name="setdepth"></a>CDumpContext:: SetDepth

Döküm derinliğini ayarlar.

```cpp
void SetDepth(int nNewDepth);
```

### <a name="parameters"></a>Parametreler

*nNewDepth*<br/>
Yeni Derinlik değeri.

### <a name="remarks"></a>Açıklamalar

Diğer nesnelere işaretçi içermeyen bir temel tür veya basit döküm oluşturuyorsanız `CObject` 0 değeri yeterlidir. 0 ' dan büyük bir değer, tüm nesnelerin yinelemeli olarak dökülebileceği derin döküm belirtir. Örneğin, bir koleksiyonun ayrıntılı bir dökümü, koleksiyonun tüm öğelerinin dökümünü alacak. Türetilmiş sınıflarınızda diğer belirli derinlik değerlerini kullanabilirsiniz.

> [!NOTE]
> Derin dökümlerde döngüsel başvurular algılanmaz ve sonsuz döngülere neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFile sınıfı](../../mfc/reference/cfile-class.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)
