---
title: CMemoryState Yapısı
ms.date: 11/04/2016
f1_keywords:
- CMemoryState
helpviewer_keywords:
- CMemoryState structure [MFC]
- memory leaks [MFC], detecting
- detecting memory leaks [MFC]
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
ms.openlocfilehash: 8f49a9faf70673c62167deeaa1bef33e4882378f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369994"
---
# <a name="cmemorystate-structure"></a>CMemoryState Yapısı

Programınızdaki bellek sızıntılarını algılamak için kullanışlı bir yol sağlar.

## <a name="syntax"></a>Sözdizimi

```
struct CMemoryState
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMemoryState::CMemoryState](#cmemorystate)|Bellek denetim noktalarını denetleyen sınıf benzeri bir yapı oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMemoryState::Denetim Noktası](#checkpoint)|Geçerli bellek durumunun anlık görüntüsünü (denetim noktası) alır.|
|[CMemoryState::Difference](#difference)|Türünden `CMemoryState`iki nesne arasındaki farkı hesaplar.|
|[CMemoryState::DumpAllObjectsSince](#dumpallobjectssince)|Önceki denetim noktasından bu yana şu anda ayrılan tüm nesnelerin bir özetini döker.|
|[CMemoryState::Dumpİstatistiki](#dumpstatistics)|Bir `CMemoryState` nesne için bellek ayırma istatistiklerini yazdırır.|

## <a name="remarks"></a>Açıklamalar

`CMemoryState`bir yapıdır ve taban sınıfa sahip değildir.

Bir nesnenin belleği yığına tahsis edildiğinde ancak artık gerekmediğinde ayrılmadığında bir "bellek sızıntısı" oluşur. Bu tür bellek sızıntıları sonunda bellek dışı hatalara yol açabilir. Programınızda bellek ayırmanın ve anlaşma yapmanın birkaç yolu vardır:

- Çalışma zamanı kitaplığından işlev `free` ailesini kullanma. `malloc` / 

- Windows API bellek yönetimi `LocalAlloc` /  `LocalFree` işlevlerini kullanma ve `GlobalAlloc` /  `GlobalFree`.

- C++ **yeni** ve **silme** işleçlerini kullanma.

Tanılama yalnızca `CMemoryState` **yeni** işleç kullanılarak ayrılan bellek **silinkullanılarak**ayrılmadığında oluşan bellek sızıntılarının algılanmalarına yardımcı olur. Bellek yönetimi işlevleri diğer iki grup olmayan C++ programları içindir ve aynı programda **yeni** ve **silme** ile karıştırma tavsiye edilmez. Bellek ayırmalarının dosya ve satır numarası takibine ihtiyaç duyduğunuzda, **yeni** işlecideğiştirmek için ek bir makro, DEBUG_NEW sağlanır. DEBUG_NEW normalde **yeni** işleci kullandığınızda kullanılır.

Diğer tanılamalarda olduğu `CMemoryState` gibi, tanılama yalnızca programınızın hata ayıklama sürümlerinde kullanılabilir. Hata ayıklama sürümü _DEBUG sabit tanımlı olmalıdır.

Programınızın bir bellek sızıntısı olduğundan şüpheleniyorsanız, `Checkpoint` `Difference`program `DumpStatistics` yürütülmesinde iki farklı noktada bellek durumu (ayrılan nesneler) arasındaki farkı keşfetmek için , ve işlevleri kullanabilirsiniz. Bu bilgiler, bir işlevin ayırdığı tüm nesneleri temizleyip temizlemediğini belirlemede yararlı olabilir.

Ayırma ve ayırmadaki dengesizlik nerede oluştuğunu bilmek yeterli bilgi sağlamazsa, önceki çağrıdan bu yana ayrılan tüm nesneleri dökümü `DumpAllObjectsSince` işlevini `Checkpoint`kullanabilirsiniz. Bu döküm, ayırma sırasını, nesnenin tahsis edildiği kaynak dosyayı ve satırı (DEBUG_NEW ayırma için kullanıyorsanız) ve nesnenin türeciliğini, adresini ve boyutunu gösterir. `DumpAllObjectsSince`ayrıca her nesnenin `Dump` işlevini geçerli durumu hakkında bilgi sağlamak için çağırır.

Nasıl kullanılacağı `CMemoryState` ve diğer tanılama hakkında daha fazla bilgi için, [Hata Ayıklama MFC Uygulamaları](/visualstudio/debugger/mfc-debugging-techniques)bakın.

> [!NOTE]
> Tür `CMemoryState` nesnelerin in bildirimleri ve üye işlevlere çağrı `#if defined(_DEBUG)/#endif` bildirimleri yönergeler tarafından parantez içinde olmalıdır. Bu, bellek tanılamanın yalnızca programınızın hata ayıklama yapılarına dahil edilmesine neden olur.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CMemoryState`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afx.h

## <a name="cmemorystatecheckpoint"></a><a name="checkpoint"></a>CMemoryState::Denetim Noktası

Belleğin anlık görüntüsünü alır ve `CMemoryState` bu nesnede saklar.

```
void Checkpoint();
```

### <a name="remarks"></a>Açıklamalar

Üye `CMemoryState` [işlevler Fark](#difference) ve [DumpAllObjectsSince](#dumpallobjectssince) bu anlık verileri kullanın.

### <a name="example"></a>Örnek

  [CMemoryState](#cmemorystate) oluşturucu için örneğe bakın.

## <a name="cmemorystatecmemorystate"></a><a name="cmemorystate"></a>CMemoryState::CMemoryState

[Checkpoint](#checkpoint) veya `CMemoryState` [Fark](#difference) üye işlevi tarafından doldurulması gereken boş bir nesne oluşturuyor.

```
CMemoryState();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

## <a name="cmemorystatedifference"></a><a name="difference"></a>CMemoryState::Difference

İki `CMemoryState` nesneyi karşılaştırır, sonra farkı `CMemoryState` bu nesneye depolar.

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>Parametreler

*oldState*<br/>
Bir `CMemoryState` denetim noktası tarafından tanımlanan ilk bellek durumu.

*newState*<br/>
Bir `CMemoryState` denetim noktası tarafından tanımlanan yeni bellek durumu.

### <a name="return-value"></a>Dönüş Değeri

İki bellek durumları farklıysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki bellek durumu parametresinin her biri için [denetim noktası](#checkpoint) çağrılmış olmalıdır.

### <a name="example"></a>Örnek

  [CMemoryState](#cmemorystate) oluşturucu için örneğe bakın.

## <a name="cmemorystatedumpallobjectssince"></a><a name="dumpallobjectssince"></a>CMemoryState::DumpAllObjectsSince

Bu `CMemoryState` nesne için son [Checkpoint](#checkpoint) çağrısından `CObject` bu yana ayrılan (ve hala tahsis edilen) sınıftan türetilen bir türdeki tüm nesneler için `Dump` işlevi çağırır.

```
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>Açıklamalar

Başlatılmamış `DumpAllObjectsSince` `CMemoryState` bir nesneyle arama, bellekte bulunan tüm nesneleri çöpe atar.

### <a name="example"></a>Örnek

  [CMemoryState](#cmemorystate) oluşturucu için örneğe bakın.

## <a name="cmemorystatedumpstatistics"></a><a name="dumpstatistics"></a>CMemoryState::Dumpİstatistiki

Fark üye işlevi tarafından doldurulan `CMemoryState` bir nesneden kısa [Difference](#difference) bir bellek istatistikleri raporu yazdırır.

```
void DumpStatistics() const;
```

### <a name="remarks"></a>Açıklamalar

[afxDump](diagnostic-services.md#afxdump) cihazında yazdırılan rapor aşağıdakileri gösterir:

Örnek bir rapor, aşağıdakilerin sayısı (veya miktarı) hakkında bilgi verir:

- ücretsiz bloklar

- normal bloklar

- CRT blokları

- blokları yok sayma

- istemci blokları

- program tarafından herhangi bir anda kullanılan maksimum bellek (baytolarak)

- program tarafından şu anda kullanılan toplam bellek (bayt olarak)

Serbest bloklar, `afxMemDF` ayarlanırsa ayırması gecikmiş blokların `delayFreeMemDF`sayısıdır. Daha fazla bilgi için " MFC Makrolar ve Küreseller" bölümündeki [afxMemDF](diagnostic-services.md#afxmemdf)bölümüne bakın.

### <a name="example"></a>Örnek

  *Projname*App.cpp'ye aşağıdaki kod yerleştirilmelidir. Aşağıdaki genel değişkenleri tanımlayın:

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

İşlevde `InitInstance` satır ekleyin:

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

`ExitInstance` İşlev için bir işleyici ekleyin ve aşağıdaki kodu kullanın:

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

Artık `DumpStatistics` işlevin çıktısını görmek için programı Hata Ayıklama modunda çalıştırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
