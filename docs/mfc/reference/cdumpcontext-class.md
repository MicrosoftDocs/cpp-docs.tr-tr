---
title: CDumpContext Sınıfı
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
ms.openlocfilehash: e89bbc5f263dc9303140e43914619090109b8315
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753213"
---
# <a name="cdumpcontext-class"></a>CDumpContext Sınıfı

Akış odaklı tanı çıktısını insan tarafından okunabilir metin biçiminde destekler.

## <a name="syntax"></a>Sözdizimi

```
class CDumpContext
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDumpContext::CdumpContext](#cdumpcontext)|Bir `CDumpContext` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDumpContext::DumpAsHex](#dumpashex)|Belirtilen öğeyi hexadecimal biçimde boşaltır.|
|[CDumpContext::Flush](#flush)|Döküm bağlam arabelleğindeki tüm verileri temizler.|
|[CDumpContext::GetDepth](#getdepth)|Çöplüğün derinliğine karşılık gelen bir bir sonsayı alır.|
|[CDumpContext::HexDump](#hexdump)|Hexadecimal formatında bir dizi de bulunan baytları boşaltır.|
|[CDumpContext::SetDepth](#setdepth)|Çöplüğün derinliğini ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CDumpContext::işleç&lt;&lt;](#operator_lt_lt)|Değişkenleri ve nesneleri döküm bağlamına ekler.|

## <a name="remarks"></a>Açıklamalar

`CDumpContext`taban sınıfa sahip değildir.

Dampinginizin çoğu için `CDumpContext` önceden bildirilmemiş bir nesne olan [afxDump'ı](diagnostic-services.md#afxdump)kullanabilirsiniz. Nesne `afxDump` yalnızca Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümünde kullanılabilir.

Bellek [tanılama hizmetlerinin](../../mfc/reference/diagnostic-services.md) `afxDump` birkaçı çıktıları için kullanılır.

Windows ortamında, önceden tanımlanmış `afxDump` nesneden gelen çıktı, kavramsal `cerr` olarak akışa benzer, Windows işlevi `OutputDebugString`aracılığıyla hata ayıkıcıya yönlendirilir.

Sınıf, `CDumpContext` nesnenin verilerini boşaltan **<<** işaretçiler `CObject` için aşırı yüklü ekleme ( ) işlecine sahiptir. Türetilen bir nesne için özel bir döküm biçimine ihtiyacınız varsa, [CObject::Dump](../../mfc/reference/cobject-class.md#dump)geçersiz kılın. Çoğu Microsoft Foundation sınıfı geçersiz `Dump` kılınmış bir üye işlev uygular.

Türetilmiş olmayan `CObject`sınıflar , `CString` `CTime`gibi `CTimeSpan`, , ve `CDumpContext` , kendi aşırı yükleme ekleme işleçleri `CFileStatus`var, gibi sık kullanılan yapılar yapmak , `CPoint`, ve `CRect`.

IMPLEMENT_DYNAMIC [veya](../../mfc/reference/run-time-object-model-services.md#implement_dynamic) [IMPLEMENT_SERIAL](../../mfc/reference/run-time-object-model-services.md#implement_serial) makroyu sınıfınızın uygulamasında kullanırsanız, türetilmiş `CObject`sınıfınızın adını `CObject::Dump` yazdırırsınız. Aksi takdirde, `CObject`yazdırAcak.

Sınıf, `CDumpContext` kitaplığın hem Hata Ayıklama hem de Sürüm `Dump` sürümlerinde kullanılabilir, ancak üye işlev yalnızca Hata Ayıklama sürümünde tanımlanır. Özel `Dump` üye işlevleriniz de dahil olmak üzere tanılama kodunuzu paranteze almak için **#ifdef _DEBUG**  /  `#endif` deyimler kullanın.

Kendi `CDumpContext` nesnenizi oluşturmadan önce, `CFile` dökümü hedef olarak hizmet veren bir nesne oluşturmanız gerekir.

Daha fazla `CDumpContext`bilgi için, [Hata Ayıklama MFC Uygulamaları'na](/visualstudio/debugger/mfc-debugging-techniques)bakın.

**#define _DEBUG**

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDumpContext`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cdumpcontextcdumpcontext"></a><a name="cdumpcontext"></a>CDumpContext::CdumpContext

Sınıfın `CDumpContext`bir nesnesini inşa eder.

```
CDumpContext(CFile* pFile = NULL);
```

### <a name="parameters"></a>Parametreler

*pFile*<br/>
Dökümü hedef `CFile` olan nesneye bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Nesne `afxDump` otomatik olarak oluşturulur.

Döküm bağlamı etkinken temele `CFile` yazmayın; aksi takdirde, dökümü ile müdahale edecektir. Windows ortamı altında, çıktı Windows işlevi `OutputDebugString`üzerinden hata ayıklama yönlendirilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#12](../../mfc/codesnippet/cpp/cdumpcontext-class_1.cpp)]

## <a name="cdumpcontextdumpashex"></a><a name="dumpashex"></a>CDumpContext::DumpAsHex

Hexadecimal sayılar olarak biçimlendirilmiş belirtilen türü boşaltır.

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

Belirtilen türdeki öğeyi hexadecimal sayı olarak dökümü için bu üye işlevi arayın. Bir diziyi dökümüiçin [CDumpContext::HexDump'ı](#hexdump)arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#13](../../mfc/codesnippet/cpp/cdumpcontext-class_2.cpp)]

## <a name="cdumpcontextflush"></a><a name="flush"></a>CDumpContext::Flush

Arabelleklerde kalan tüm verileri döküm bağlamına eklenen dosyaya yazılmaya zorlar.

```cpp
void Flush();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#14](../../mfc/codesnippet/cpp/cdumpcontext-class_3.cpp)]

## <a name="cdumpcontextgetdepth"></a><a name="getdepth"></a>CDumpContext::GetDepth

Derin veya sığ bir dökümün işlem de olsa olup olmadığını belirler.

```
int GetDepth() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tarafından ayarlanan dökümün `SetDepth`derinliği.

### <a name="example"></a>Örnek

  [SetDepth](#setdepth)örneğine bakın.

## <a name="cdumpcontexthexdump"></a><a name="hexdump"></a>CDumpContext::HexDump

Hexadecimal sayılar olarak biçimlendirilmiş bir dizi bayt boşaltır.

```cpp
void HexDump(
    LPCTSTR lpszLine,
    BYTE* pby,
    int nBytes,
    int nWidth);
```

### <a name="parameters"></a>Parametreler

*lpszLine*<br/>
Yeni bir satırın başında çıktı için bir dize.

*pby*<br/>
Dökümü için bayt içeren bir arabellek için bir işaretçi.

*nBayt*<br/>
Dökecek bayt sayısı.

*Nwidth*<br/>
Satır başına atılan maksimum bayt sayısı (çıktı satırının genişliği değil).

### <a name="remarks"></a>Açıklamalar

Hexadecimal sayı olarak tek, belirli bir madde türünü dökümü için [CDumpContext::DumpAsHex'](#dumpashex)i arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#15](../../mfc/codesnippet/cpp/cdumpcontext-class_4.cpp)]

## <a name="cdumpcontextoperator-ltlt"></a><a name="operator_lt_lt"></a>CDumpContext::işleç&lt;&lt;

Belirtilen verileri döküm bağlamına çıkar.

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

Bir `CDumpContext` referans. İade değerini kullanarak, tek bir kaynak kodu satırına birden çok ekleme yazabilirsiniz.

### <a name="remarks"></a>Açıklamalar

Ekleme işleci işaretçilerin yanı `CObject` sıra çoğu ilkel tür için aşırı yüklenir. Karakter işaretçisi dize içeriğinin dökümüyle sonuçlanır; **geçersiz** kılmak için bir işaretçi yalnızca adresin hexadecimal dökümü ile sonuçlanır. Uzun bir sonuç 64 bit imzalı bir tamstamsız çöplük; ULONGLONG, 64 bit imzasız bir tamstamSız Çöplüğüne neden olabilir.

IMPLEMENT_DYNAMIC veya IMPLEMENT_SERIAL makroyu sınıfınızın uygulanmasında kullanırsanız, ekleme işleci , `CObject::Dump`"türetilmiş sınıfınızın `CObject`adını yazdırır" yoluyla yazdırır. Aksi takdirde, `CObject`yazdırAcak. Sınıfın `Dump` işlevini geçersiz kılarsanız, hexadecimal dökümü yerine nesnenin içeriğinin daha anlamlı bir çıktısını sağlayabilirsiniz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#17](../../mfc/codesnippet/cpp/cdumpcontext-class_5.cpp)]

## <a name="cdumpcontextsetdepth"></a><a name="setdepth"></a>CDumpContext::SetDepth

Çöplüğün derinliğini ayarlar.

```cpp
void SetDepth(int nNewDepth);
```

### <a name="parameters"></a>Parametreler

*nNewDepth*<br/>
Yeni derinlik değeri.

### <a name="remarks"></a>Açıklamalar

Diğer nesnelere işaretçi içermeyen `CObject` ilkel bir türü veya basiti boşaltıyorsanız, 0 değeri yeterlidir. 0'dan büyük bir değer, tüm nesnelerin özyinelemeli olarak döküldüğü derin bir dökümü belirtir. Örneğin, koleksiyonun derin bir dökümü koleksiyonun tüm öğelerini döker. Türemiş sınıflarınızda diğer belirli derinlik değerlerini kullanabilirsiniz.

> [!NOTE]
> Dairesel başvurular derin dökümlerde algılanmaz ve sonsuz döngülere neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#16](../../mfc/codesnippet/cpp/cdumpcontext-class_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CFile Sınıfı](../../mfc/reference/cfile-class.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)
