---
title: MFC Tarafından Kullanılan Geri Çağırma İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: 9e51774b2158a81fce05dc0bd27e296e4ad94faa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507706"
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

## <a name="enum_objects"></a>CDC:: EnumObjects için geri çağırma Işlevi

*Objectfunc* adı, uygulama tarafından sağlanan işlev adı için bir yer tutucudur.

### <a name="syntax"></a>Sözdizimi

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>Parametreler

*lpszLogObject*<br/>
Nesnenin mantıksal öznitelikleri hakkında bilgi içeren bir [logpen](/windows/win32/api/Wingdi/ns-wingdi-logpen) veya [LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) veri yapısına işaret eder.

*lpData*<br/>
`EnumObjects` İşleve geçirilen uygulama tarafından sağlanan verileri işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Geri çağırma işlevi bir **int**döndürür. Bu döndürün değeri Kullanıcı tanımlı ' dır. Geri çağırma işlevi 0 döndürürse, `EnumObjects` numaralandırmayı erken durdur.

### <a name="remarks"></a>Açıklamalar

Asıl ad verilmelidir.

## <a name="graystring"></a>CDC:: gri dize için geri çağırma Işlevi

*OutputFunc* , uygulama tarafından sağlanan geri çağırma işlev adı için bir yer tutucudur.

### <a name="syntax"></a>Sözdizimi

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>Parametreler

*hDC*<br/>
En azından, `nWidth` `nHeight`veile belirtilen genişlik ve yüksekliğin bit eşlemiyle bir bellek cihazı bağlamını tanımlar. `GrayString`

*lpData*<br/>
Çizilecek karakter dizesine işaret eder.

*nCount*<br/>
Çıktının kaç karakter sayısını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Geri çağırma işlevinin dönüş değeri başarıyı göstermek için TRUE olmalıdır; Aksi takdirde, FALSE olur.

### <a name="remarks"></a>Açıklamalar

Geri çağırma işlevi (*OutputFunc*), (*x*, *y*) yerine koordinatlara (0, 0) göre bir resim çizmelidir.

## <a name="setabortproc"></a>CDC:: SetAbortProc için geri çağırma Işlevi

*Abortfunc* adı, uygulama tarafından sağlanan işlev adı için bir yer tutucudur.

### <a name="syntax"></a>Sözdizimi

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>Parametreler

*hPr*<br/>
Cihaz bağlamını tanımlar.

*kodudur*<br/>
Bir hata oluşup oluşmadığını belirtir. Herhangi bir hata oluştuysa 0 ' dır. Yazdırma yöneticisinin şu anda disk alanı tükendiğini ve uygulamanın beklediği durumlarda daha fazla disk alanının kullanılabilir olacağını SP_OUTOFDISK. *Kod* SP_OUTOFDISK ise, uygulamanın yazdırma işini iptal etmek zorunda değildir. Değilse, `PeekMessage` veya `GetMessage` Windows işlevini çağırarak yazdırma Yöneticisi 'ne vermelidir.

### <a name="return-value"></a>Dönüş Değeri

Yazdırma işi devam edebiliyorsanız ve iptal edilirse 0, Abort-Handler işlevinin dönüş değeri sıfır değildir.

### <a name="remarks"></a>Açıklamalar

Asıl ad, [CDC:: SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)' nin açıklamalar bölümünde açıklandığı gibi verilmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC:: EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC:: gri dize](../../mfc/reference/cdc-class.md#graystring)
