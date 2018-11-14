---
title: CMemoryState yapısı
ms.date: 11/04/2016
f1_keywords:
- CMemoryState
helpviewer_keywords:
- CMemoryState structure [MFC]
- memory leaks [MFC], detecting
- detecting memory leaks [MFC]
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
ms.openlocfilehash: 5aee7bc2f44e4c2e7851baea554d3069c928088c
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523435"
---
# <a name="cmemorystate-structure"></a>CMemoryState yapısı

Programınızda bellek sızıntılarını algılamak için kullanışlı bir yol sağlar.

## <a name="syntax"></a>Sözdizimi

```
struct CMemoryState
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMemoryState::CMemoryState](#cmemorystate)|Bellek denetim noktaları denetleyen bir sınıf benzeri yapısı oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMemoryState::Checkpoint](#checkpoint)|Geçerli bellek durumunun bir anlık görüntü (Denetim) alır.|
|[CMemoryState::Difference](#difference)|Türünden iki nesne arasındaki farkı hesaplar `CMemoryState`.|
|[CMemoryState::DumpAllObjectsSince](#dumpallobjectssince)|Şu anda ayrılmış olan tüm nesnelerin bir özeti, önceki bir denetim noktası beri dökümünü yapar.|
|[CMemoryState::DumpStatistics](#dumpstatistics)|Bellek ayırma istatistiklerini yazdırır bir `CMemoryState` nesne.|

## <a name="remarks"></a>Açıklamalar

`CMemoryState` bir yapı olduğunu ve bir temel sınıfa sahip değil.

Bir nesne için bellek yığında ayrılmış ancak artık gerekli olmadığında serbest değil "Bellek sızıntısı" oluşuyor. Bu tür bellek sızıntılarını, sonunda bellek yetersiz hatalara yol açabilir. Ayırma ve programınızdaki bellek ayırması için birçok yol vardır:

- Kullanarak `malloc` /  `free` işlevler Çalışma Zamanı Kitaplığı'ndan ailesi.

- Windows API bellek yönetimi işlevleri kullanarak `LocalAlloc` /  `LocalFree` ve `GlobalAlloc` /  `GlobalFree`.

- C++ kullanarak **yeni** ve **Sil** işleçleri.

`CMemoryState` Tanılama yalnızca bellek belirlenmesine yardımcı ölçeklendiremediğinde meydana kullanarak ayrılan bellek sızıntılarını **yeni** işleci serbest kullanarak **Sil**. Diğer iki bellek yönetimi işlevleri harici C++ programları ve bunları ile karıştırma gruplarıdır **yeni** ve **Sil** aynı programda önerilmez. DEBUG_NEW, ek bir makro değiştirmek için sağlanan **yeni** , dosya ve satır numarası izleme bellek ayırmaları gerektiğinde işleci. Normalde her DEBUG_NEW kullanılan **yeni** işleci.

Diğer tanılama olduğu gibi ile `CMemoryState` tanılama bulunan ve yalnızca, programınızın hata ayıklama sürümleri. Hata ayıklama sürümü _DEBUG sabitinin tanımlanmasını olması gerekir.

Programınızda bir bellek sızıntısı şüpheleniyorsanız, kullanabileceğiniz `Checkpoint`, `Difference`, ve `DumpStatistics` program yürütmesinde farklı noktalarda iki bellek durumu (ayrılan nesneler) arasındaki fark bulmak için işlevleri. Bu bilgiler, ayırdığı tüm nesneleri bir işlev temizleme olup olmadığını belirlemede faydalı olabilir.

Yalnızca ayırmayı ve ayırmayı kaldırma dengesizliği nerede oluştuğunu bilmek yeterli bilgi sağlamazsa, kullanabileceğiniz `DumpAllObjectsSince` önceki çağrısından itibaren ayrılan tüm nesnelerin dökümünü almak için işlev `Checkpoint`. Bu döküm ayırma, kaynak dosyasını ve burada nesne tahsis edildiğinde (DEBUG_NEW ayırma için kullanıyorsanız), satır sırasını gösterir ve nesnenin adresini ve boyutunu türetmede. `DumpAllObjectsSince` Ayrıca her nesnenin çağırır `Dump` geçerli durumu hakkında bilgi sağlamak için işlevi.

Nasıl kullanılacağı hakkında daha fazla bilgi için `CMemoryState` ve diğer tanılama [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques).

> [!NOTE]
>  Nesne türü bildirimleri `CMemoryState` ve üye işlevleri çağrıları bracketed tarafından `#if defined(_DEBUG)/#endif` yönergeleri. Bu, yalnızca programınızın hata ayıklama yapılarında olarak eklenecek Bellek Tanılama neden olur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CMemoryState`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afx.h

##  <a name="checkpoint"></a>  CMemoryState::Checkpoint

Bellek Özet anlık görüntüsünü alır ve bu depolar `CMemoryState` nesne.

```
void Checkpoint();
```

### <a name="remarks"></a>Açıklamalar

`CMemoryState` Üye işlevleri [fark](#difference) ve [DumpAllObjectsSince](#dumpallobjectssince) bu anlık görüntü verilerini kullan.

### <a name="example"></a>Örnek

  Örneğin bakın [CMemoryState](#cmemorystate) Oluşturucusu.

##  <a name="cmemorystate"></a>  CMemoryState::CMemoryState

Boş bir yapıları `CMemoryState` tarafından doldurulmalıdır nesne [denetim noktası](#checkpoint) veya [fark](#difference) üye işlevi.

```
CMemoryState();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

##  <a name="difference"></a>  CMemoryState::Difference

İki karşılaştırır `CMemoryState` nesneleri sonra bu içine fark depolar `CMemoryState` nesne.

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>Parametreler

*Eski*<br/>
İlk bellek durumu tarafından tanımlandığı gibi bir `CMemoryState` denetim noktası.

*Durum*<br/>
Yeni bellek durumu tarafından tanımlanan bir `CMemoryState` denetim noktası.

### <a name="return-value"></a>Dönüş Değeri

İki bellek durumu farklı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

[Denetim noktası](#checkpoint) her iki bellek durumu parametreleri için çağrılmışsa gerekir.

### <a name="example"></a>Örnek

  Örneğin bakın [CMemoryState](#cmemorystate) Oluşturucusu.

##  <a name="dumpallobjectssince"></a>  CMemoryState::DumpAllObjectsSince

Çağrıları `Dump` işlevi bir türdeki tüm nesneler için sınıfından türetilmiş `CObject` ayrılan (ve hala ayrılır) son [denetim noktası](#checkpoint) bu çağrı `CMemoryState` nesne.

```
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>Açıklamalar

Çağırma `DumpAllObjectsSince` başlatılmamış bir ile `CMemoryState` nesne bellekte bulunan tüm nesneleri dökümü.

### <a name="example"></a>Örnek

  Örneğin bakın [CMemoryState](#cmemorystate) Oluşturucusu.

##  <a name="dumpstatistics"></a>  CMemoryState::DumpStatistics

Kısa bellek istatistikleri rapordan yazdırır bir `CMemoryState` tarafından doldurulur nesne [fark](#difference) üye işlevi.

```
void DumpStatistics() const;
```

### <a name="remarks"></a>Açıklamalar

Yazdırılır rapor [afxDump](diagnostic-services.md#afxdump) cihaz, aşağıdaki gösterir:

Bir örnek bildirim raporu sayı (veya tutar) hakkında bilgi sağlar:

- boş blok

- Normal blokları

- CRT blokları

- blokları yoksay

- istemci blokları

- Maksimum bellek (bayt cinsinden) herhangi bir zamanda program tarafından kullanılan

- şu anda program (bayt cinsinden) tarafından kullanılan toplam bellek

Ücretsiz taşlarıdır olan ayırmayı kaldırma durumunda gecikti bloğu `afxMemDF` ayarlandı `delayFreeMemDF`. Daha fazla bilgi için [afxMemDF](diagnostic-services.md#afxmemdf), "MFC makroları ve genel öğeleri" bölümünde.

### <a name="example"></a>Örnek

  Aşağıdaki kod yerleştirilmelidir *projname*App.cpp. Aşağıdaki genel değişkenleri tanımlayın:

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

İçinde `InitInstance` işlevi, satırı ekleyin:

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

İçin bir işleyici eklemek `ExitInstance` işlev ve aşağıdaki kodu kullanın:

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

Şimdi programı çıktısını görmek için hata ayıklama modunda çalıştırabilirsiniz `DumpStatistics` işlevi.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

