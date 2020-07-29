---
title: MFC Tarafından Kullanılan Geri Çağırma İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: 19c0bd3a0685abe36c020a5dda930f5683a4baa9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87183441"
---
# <a name="callback-functions-used-by-mfc"></a>MFC Tarafından Kullanılan Geri Çağırma İşlevleri

Microsoft Foundation Class Kitaplığı üç geri çağırma işlevi görüntülenir. Bu geri çağırma işlevleri [CDC:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC:: Gristring](../../mfc/reference/cdc-class.md#graystring)ve [CDC:: SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)' a geçirilir. Tüm geri çağrı işlevlerinin, geri çağırma sınırları genelinde özel durumlar gerçekleştirilemediğinden, Windows 'a döndürmeden önce MFC özel durumlarını yakalamasını gerektiğini unutmayın. Özel durumlar hakkında daha fazla bilgi için bkz. Makale [özel durumları](../../mfc/exception-handling-in-mfc.md).

|Ad||
|----------|-----------------|
|[CDC::EnumObjects için Geri Çağırma İşlevi](#enum_objects)||
|[CDC::GrayString için Geri Çağırma İşlevi](#graystring)||
|[CDC::SetAbortProc için Geri Çağırma İşlevi](#setabortproc)||

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="callback-function-for-cdcenumobjects"></a><a name="enum_objects"></a>CDC:: EnumObjects için geri çağırma Işlevi

*Objectfunc* adı, uygulama tarafından sağlanan işlev adı için bir yer tutucudur.

### <a name="syntax"></a>Söz dizimi

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>Parametreler

*lpszLogObject*<br/>
Nesnenin mantıksal öznitelikleri hakkında bilgi içeren bir [logpen](/windows/win32/api/Wingdi/ns-wingdi-logpen) veya [LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) veri yapısına işaret eder.

*lpData*<br/>
İşleve geçirilen uygulama tarafından sağlanan verileri işaret eder `EnumObjects` .

### <a name="return-value"></a>Dönüş Değeri

Geri çağırma işlevi bir döndürür **`int`** . Bu döndürün değeri Kullanıcı tanımlı ' dır. Geri çağırma işlevi 0 döndürürse, `EnumObjects` numaralandırmayı erken durdur.

### <a name="remarks"></a>Açıklamalar

Asıl ad verilmelidir.

## <a name="callback-function-for-cdcgraystring"></a><a name="graystring"></a>CDC:: gri dize için geri çağırma Işlevi

*OutputFunc* , uygulama tarafından sağlanan geri çağırma işlev adı için bir yer tutucudur.

### <a name="syntax"></a>Söz dizimi

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>Parametreler

*hDC*<br/>
En azından, ve ile belirtilen genişlik ve yüksekliğin bit eşlemiyle bir bellek cihazı bağlamını `nWidth` tanımlar `nHeight` `GrayString` .

*lpData*<br/>
Çizilecek karakter dizesine işaret eder.

*nCount*<br/>
Çıktının kaç karakter sayısını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Geri çağırma işlevinin dönüş değeri başarıyı göstermek için TRUE olmalıdır; Aksi takdirde, FALSE olur.

### <a name="remarks"></a>Açıklamalar

Geri çağırma işlevi (*OutputFunc*), (*x*, *y*) yerine koordinatlara (0, 0) göre bir resim çizmelidir.

## <a name="callback-function-for-cdcsetabortproc"></a><a name="setabortproc"></a>CDC:: SetAbortProc için geri çağırma Işlevi

*Abortfunc* adı, uygulama tarafından sağlanan işlev adı için bir yer tutucudur.

### <a name="syntax"></a>Söz dizimi

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>Parametreler

*hPr*<br/>
Cihaz bağlamını tanımlar.

*kodudur*<br/>
Bir hata oluşup oluşmadığını belirtir. Herhangi bir hata oluştuysa 0 ' dır. Yazdırma yöneticisinin şu anda disk alanı tükenme ve uygulama bekliyorsa daha fazla disk alanı kullanılabilir hale gelmesi SP_OUTOFDISK. *Kod* SP_OUTOFDISK ise, uygulamanın yazdırma işini iptal etmek zorunda değildir. Değilse, `PeekMessage` veya Windows işlevini çağırarak yazdırma Yöneticisi 'ne vermelidir `GetMessage` .

### <a name="return-value"></a>Dönüş Değeri

Yazdırma işi devam edebiliyorsanız ve iptal edilirse 0, Abort-Handler işlevinin dönüş değeri sıfır değildir.

### <a name="remarks"></a>Açıklamalar

Asıl ad, [CDC:: SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)' nin açıklamalar bölümünde açıklandığı gibi verilmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC:: SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC:: gri dize](../../mfc/reference/cdc-class.md#graystring)
