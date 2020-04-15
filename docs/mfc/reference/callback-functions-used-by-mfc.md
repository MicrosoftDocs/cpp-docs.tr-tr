---
title: MFC Tarafından Kullanılan Geri Çağırma İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- callback functions [MFC], MFC
- MFC, callback functions
- functions [MFC], callback
- callback functions [MFC]
ms.assetid: b2a6857c-fdd3-45ec-8fd8-2e71fac77582
ms.openlocfilehash: 8d84f939795e768c6b1356dcd8dc291421aedfdc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371133"
---
# <a name="callback-functions-used-by-mfc"></a>MFC Tarafından Kullanılan Geri Çağırma İşlevleri

Microsoft Hazırlık Sınıfı Kitaplığı'nda üç geri arama işlevi görünür. Bu geri arama işlevleri [CDC geçirilir::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects), [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring), ve [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc). Özel durumlar geri arama sınırları dışına atılamayacağından, tüm geri arama işlevlerinin Windows'a dönmeden önce MFC özel durumlarını hapsetmesi gerektiğini unutmayın. Özel durumlar hakkında daha fazla bilgi için [özel durumlar](../../mfc/exception-handling-in-mfc.md)makalesine bakın.

|Adı||
|----------|-----------------|
|[CDC::EnumObjects için Geri Çağırma İşlevi](#enum_objects)||
|[CDC::GrayString için Geri Çağırma İşlevi](#graystring)||
|[CDC::SetAbortProc için Geri Çağırma İşlevi](#setabortproc)||

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="callback-function-for-cdcenumobjects"></a><a name="enum_objects"></a>CDC için Geri Arama Fonksiyonu::EnumObjects

*ObjectFunc* adı, uygulama tarafından sağlanan işlev adı için bir yer tutucudur.

### <a name="syntax"></a>Sözdizimi

```
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,
    LPSTR* lpData);
```

### <a name="parameters"></a>Parametreler

*lpszLogNesne*<br/>
Nesnenin mantıksal öznitelikleri hakkında bilgi içeren bir [LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen) veya [LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) veri yapısına işaret eder.

*lpData*<br/>
`EnumObjects` İşlev için geçirilen uygulama tarafından sağlanan verilere işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Geri arama işlevi bir **int**döndürür. Bu iadenin değeri kullanıcı tarafından tanımlanır. Geri arama işlevi 0 `EnumObjects` döndürürse, numaralandırmayı erken durdurur.

### <a name="remarks"></a>Açıklamalar

Gerçek ad dışa aktarılmalıdır.

## <a name="callback-function-for-cdcgraystring"></a><a name="graystring"></a>CDC için Geri Arama Fonksiyonu::GrayString

*OutputFunc,* uygulama tarafından sağlanan geri arama işlevi adı için bir yer tutucudur.

### <a name="syntax"></a>Sözdizimi

```
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,
    LPARAM lpData,
    int nCount);
```

### <a name="parameters"></a>Parametreler

*Hdc*<br/>
Bellek aygıtı bağlamını en az belirtilen genişlik ve `nWidth` yüksekte `GrayString`bir bit eşlemi ile tanımlar. `nHeight`

*lpData*<br/>
Çizilecek karakter dizesine işaret eder.

*nSayısı*<br/>
Çıktıiçin karakter sayısını belirtir.

### <a name="return-value"></a>Dönüş Değeri

Geri arama işlevinin geri dönüş değeri başarıyı göstermek için TRUE olmalıdır; aksi takdirde FALSE olduğunu.

### <a name="remarks"></a>Açıklamalar

Geri arama işlevi *(OutputFunc)* yerine koordinatları (0,0) görebir görüntü çizmek gerekir (*x*, *y*).

## <a name="callback-function-for-cdcsetabortproc"></a><a name="setabortproc"></a>CDC için Geri Arama Fonksiyonu::SetAbortProc

*AbortFunc* adı, uygulama tarafından sağlanan işlev adı için bir yer tutucudur.

### <a name="syntax"></a>Sözdizimi

```
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,
    int code);
```

### <a name="parameters"></a>Parametreler

*Hpr*<br/>
Aygıt bağlamını tanımlar.

*Kod*<br/>
Bir hata nın oluşup oluşmadığını belirtir. Hata oluştuysa 0'dır. Yazdırma Yöneticisi şu anda disk alanı dışında ysa ve uygulama beklerse daha fazla disk alanı kullanılabilir hale gelirse SP_OUTOFDISK. *Kod* SP_OUTOFDISK ise, uygulamayazdırma işini iptal etmek zorunda değildir. Yoksa, Yazdırma Yöneticisi'ne `PeekMessage` `GetMessage` veya Windows işlevini arayarak teslim olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Yazdırma işi devam edecekse iptal işleyici işlevinin geri dönüş değeri sıfırsız, iptal edilirse 0 olur.

### <a name="remarks"></a>Açıklamalar

Gerçek ad CDC Açıklamalar bölümünde açıklandığı gibi dışa [aktarılmalıdır::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc).

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Aramalar ve İleti Haritaları](structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)<br/>
[CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc)<br/>
[CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)
