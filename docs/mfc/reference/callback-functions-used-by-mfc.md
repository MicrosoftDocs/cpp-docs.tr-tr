---
title: MFC Tarafından Kullanılan Geri Çağırma İşlevleri
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.functions
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: acb7b6c677d03ef1320e24373671a7577c2ccda8
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178440"
---
# <a name="callback-functions-used-by-mfc"></a>MFC Tarafından Kullanılan Geri Çağırma İşlevleri

Üç geri çağırma işlevleri, Microsoft Foundation Class Kitaplığı ' görünür. Bu geri arama işlevlerine geçirilen [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring), ve [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc). Windows için özel durumlar, geri çağırma sınırlarında atılamıyor beri döndürmeden önce MFC özel durumları tüm geri çağırma işlevleri tuzak, gerekir unutmayın. Özel durumları hakkında daha fazla bilgi için bkz [özel durumları](../../mfc/exception-handling-in-mfc.md).

|Ad||
|----------|-----------------|
|[CDC::EnumObjects için Geri Çağırma İşlevi](#enum_objects)||
|[CDC::GrayString için Geri Çağırma İşlevi](#graystring)||
|[CDC::SetAbortProc için Geri Çağırma İşlevi](#setabortproc)||

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

## <a name="enum_objects"></a> CDC::EnumObjects için geri çağırma işlevi

*ObjectFunc* adı uygulama tarafından sağlanan işlev adı için bir yer tutucudur.

### <a name="syntax"></a>Sözdizimi

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>Parametreler

*lpszLogObject*<br/>
İşaret eden bir [LOGPEN](/windows/desktop/api/Wingdi/ns-wingdi-taglogpen) veya [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) nesnenin mantıksal öznitelikleri hakkında bilgi içeren veri yapısı.

*lpData*<br/>
Uygulama tarafından sağlanan veri noktalarına geçirilen `EnumObjects` işlevi.

### <a name="return-value"></a>Dönüş Değeri

Geri çağırma işlevi bir **int**. Bu dönüş değeri, kullanıcı tanımlı. Geri çağırma işlevi, 0, döndürürse `EnumObjects` erken numaralandırma durdurur.

### <a name="remarks"></a>Açıklamalar

Gerçek adı verilmesi gerekir.

## <a name="graystring"></a>  CDC::GrayString için geri çağırma işlevi

*OutputFunc* uygulama tarafından sağlanan geri çağırma işlevi adı için bir yer tutucudur.

### <a name="syntax"></a>Sözdizimi

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>Parametreler

*hDC*<br/>
Bir bellek cihaz bağlamı ile en az bir bit eşlem tanımlar genişlik ve yükseklik tarafından belirtilen `nWidth` ve `nHeight` için `GrayString`.

*lpData*<br/>
Çizilecek karakter dizesine işaret eder.

*nCount*<br/>
Çıktı olarak karakter sayısını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Geri çağırma işlevinin dönüş değeri başarılı olduğunu belirtmek için TRUE olmalıdır; Aksi takdirde yanlış olur.

### <a name="remarks"></a>Açıklamalar

Geri çağırma işlevi (*OutputFunc*) (0,0) koordinatlarına göre bir görüntü çizin gerekir yerine (*x*, *y*).

## <a name="setabortproc"></a>  CDC::SetAbortProc için geri çağırma işlevi

Adı *AbortFunc* uygulama tarafından sağlanan işlev adı için bir yer tutucudur.

### <a name="syntax"></a>Sözdizimi

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>Parametreler

*hPr*<br/>
Cihaz bağlamı tanımlar.

*Kod*<br/>
Bir hata oluşup oluşmadığını belirtir. Herhangi bir hata oluştuysa, 0'dır. Uygulamayı bekliyorsa daha fazla disk alanını kullanılabilir hale gelir ve Yazdırma Yöneticisi'ni şu anda disk alanı yetersiz olduğu SP_OUTOFDISK olduğu. Varsa *kod* olduğu SP_OUTOFDISK, yazdırma işi iptal etmek uygulama yok. Kullanmıyorsa, onu Yazdırma Yöneticisi çağırarak yield gerekir `PeekMessage` veya `GetMessage` Windows işlevi.

### <a name="return-value"></a>Dönüş Değeri

Yazdırma işi devam etmek için ise sıfır olmayan ve 0 iptal işleyicisi işlevin dönüş değeri, iptal edilirse.

### <a name="remarks"></a>Açıklamalar

Gerçek adı, açıklamalar bölümünde anlatıldığı gibi dışarı aktarılmalıdır [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc).

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)

