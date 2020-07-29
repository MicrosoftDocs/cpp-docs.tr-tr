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
ms.openlocfilehash: 823d424620e205d14f247a147bbf7dcb40a626b9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222920"
---
# <a name="cmemorystate-structure"></a>CMemoryState yapısı

Programınızdaki bellek sızıntılarını algılamaya yönelik kolay bir yol sağlar.

## <a name="syntax"></a>Sözdizimi

```
struct CMemoryState
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMemoryState:: CMemoryState](#cmemorystate)|Bellek denetim noktalarını denetleyen sınıf benzeri bir yapı oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMemoryState:: Checkpoint](#checkpoint)|Geçerli bellek durumunun anlık görüntüsünü (Checkpoint) alır.|
|[CMemoryState::D ifference](#difference)|Türü iki nesne arasındaki farkı hesaplar `CMemoryState` .|
|[CMemoryState::D umpAllObjectsSince](#dumpallobjectssince)|Önceki bir kontrol noktasından bu yana, ayrılmış olan tüm nesnelerin özetini döker.|
|[CMemoryState::D öncelik Istatistikleri](#dumpstatistics)|Bir nesne için bellek ayırma istatistiklerini yazdırır `CMemoryState` .|

## <a name="remarks"></a>Açıklamalar

`CMemoryState`bir yapıdır ve temel bir sınıfa sahip değildir.

Bir nesnenin belleği yığında ayrıldığında ancak artık gerekli olmadığında serbest bırakılmadığında "bellek sızıntısı" oluşur. Bu tür bellek sızıntıları sonunda bellek yetersiz hatalara neden olabilir. Programınızda bellek ayırmayı ve serbest bırakmak için çeşitli yollar vardır:

- `malloc` /  `free` Çalışma zamanı kitaplığındaki işlev ailesini kullanma.

- Windows API bellek yönetimi işlevlerini ve ' yi kullanma `LocalAlloc` /  `LocalFree` `GlobalAlloc` /  `GlobalFree` .

- C++ **`new`** ve işleçlerini kullanma **`delete`** .

`CMemoryState`Tanılama yalnızca işleci kullanılarak ayrılan bellek, **`new`** kullanılarak serbest bırakılmadığında oluşan bellek sızıntılarını algılamaya yardımcı olur **`delete`** . Diğer iki bellek yönetimi işlevi grubu, C + + olmayan programlar içindir ve bunları **`new`** aynı programda ve ile karıştırmaya **`delete`** önerilmez. **`new`** Bellek ayırmalarının dosya ve satır numarası izlemesine ihtiyacınız olduğunda işlecin yerini almak için DEBUG_NEW ek bir makro sağlanır. DEBUG_NEW, normalde işlecini her kullandığınızda kullanılır **`new`** .

Diğer tanılamalarda olduğu gibi, `CMemoryState` Tanılamalar yalnızca programınızın hata ayıklama sürümlerinde kullanılabilir. Hata ayıklama sürümünde _DEBUG sabit tanımlanmış olmalıdır.

Programınızın bellek sızıntısı olduğunu düşünüyorsanız,, `Checkpoint` `Difference` ve işlevlerini kullanarak, `DumpStatistics` Program yürütmesindeki iki farklı noktada bellek durumu (ayrılan nesneler) arasındaki farkı keşfedebilirsiniz. Bu bilgiler, bir işlevin ayırdığı tüm nesneleri temizleyip temizedilmeyeceğini belirlemek için yararlı olabilir.

Yalnızca ayırma ve ayırmayı kaldırma işleminin ne olduğunu bilmenin yeterli bilgi sağlamıyorsa, `DumpAllObjectsSince` Bu işlevi kullanarak, önceki çağrısından bu yana ayrılan tüm nesnelerin dökümünü alabilirsiniz `Checkpoint` . Bu döküm, ayırmanın sırasını, kaynak dosyayı ve nesnenin ayrıldığı satırı (ayırma için DEBUG_NEW kullanıyorsanız), nesnenin elde edilmesini, adresini ve boyutunu gösterir. `DumpAllObjectsSince`Ayrıca `Dump` , geçerli durumu hakkında bilgi sağlamak için her nesnenin işlevini çağırır.

Ve diğer tanılamaları kullanma hakkında daha fazla bilgi için `CMemoryState` bkz. [MFC uygulamalarında hata ayıklama](/visualstudio/debugger/mfc-debugging-techniques).

> [!NOTE]
> Türündeki nesnelerin bildirimleri `CMemoryState` ve üye işlevlerine yapılan çağrılar, yönergeler tarafından parantez içine alınmalıdır `#if defined(_DEBUG)/#endif` . Bu, bellek tanılamalarını yalnızca programınızın hata ayıklamasına dahil edilmesini sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CMemoryState`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

## <a name="cmemorystatecheckpoint"></a><a name="checkpoint"></a>CMemoryState:: Checkpoint

Belleğin anlık görüntü özetini alır ve bu `CMemoryState` nesnede depolar.

```cpp
void Checkpoint();
```

### <a name="remarks"></a>Açıklamalar

`CMemoryState`Üye Işlevleri [fark](#difference) ve [DumpAllObjectsSince](#dumpallobjectssince) bu anlık görüntü verilerini kullanır.

### <a name="example"></a>Örnek

  [CMemoryState](#cmemorystate) oluşturucusunun örneğine bakın.

## <a name="cmemorystatecmemorystate"></a><a name="cmemorystate"></a>CMemoryState:: CMemoryState

`CMemoryState` [Denetim noktası](#checkpoint) veya [fark](#difference) üye işlevi tarafından doldurulması gereken boş bir nesne oluşturur.

```
CMemoryState();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

## <a name="cmemorystatedifference"></a><a name="difference"></a>CMemoryState::D ifference

İki `CMemoryState` nesneyi karşılaştırır ve sonra farkı bu `CMemoryState` nesneye depolar.

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>Parametreler

*Eski durum*<br/>
Bir denetim noktası tarafından tanımlanan ilk bellek durumu `CMemoryState` .

*Yeni durum*<br/>
Bir denetim noktası tarafından tanımlanan yeni bellek durumu `CMemoryState` .

### <a name="return-value"></a>Dönüş Değeri

İki bellek durumu farklıysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki bellek durumu parametresi için [denetim noktası](#checkpoint) çağrılmalıdır.

### <a name="example"></a>Örnek

  [CMemoryState](#cmemorystate) oluşturucusunun örneğine bakın.

## <a name="cmemorystatedumpallobjectssince"></a><a name="dumpallobjectssince"></a>CMemoryState::D umpAllObjectsSince

`Dump` `CObject` Bu nesne Için Son [denetim noktası](#checkpoint) çağrısından bu yana ayrılan (ve hala ayrılan) sınıfından türetilmiş bir türün tüm nesneleri için işlevini çağırır `CMemoryState` .

```cpp
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>Açıklamalar

`DumpAllObjectsSince`Başlatılmamış bir nesneyle çağırmak `CMemoryState` , şu anda bellekte olan tüm nesneleri dökümünü alacak.

### <a name="example"></a>Örnek

  [CMemoryState](#cmemorystate) oluşturucusunun örneğine bakın.

## <a name="cmemorystatedumpstatistics"></a><a name="dumpstatistics"></a>CMemoryState::D öncelik Istatistikleri

`CMemoryState` [Fark](#difference) üye işlevi tarafından doldurulan bir nesneden kısa bir bellek istatistikleri raporu yazdırır.

```cpp
void DumpStatistics() const;
```

### <a name="remarks"></a>Açıklamalar

[AfxDump](diagnostic-services.md#afxdump) cihazında yazdırılan rapor, aşağıdakileri gösterir:

Örnek rapor, ' nin numarası (veya miktarı) hakkında bilgi verir:

- Ücretsiz bloklar

- normal bloklar

- CRT bloklar

- blokları yoksay

- istemci blokları

- program tarafından herhangi bir anda kullanılan en fazla bellek (bayt cinsinden)

- program tarafından şu anda kullanılan toplam bellek (bayt cinsinden)

Serbest bloklar, olarak ayarlandıysa, ayırmayı kaldırma geciktirilen blokların sayısıdır `afxMemDF` `delayFreeMemDF` . Daha fazla bilgi için bkz. "MFC makroları ve genel" bölümünde [afxMemDF](diagnostic-services.md#afxmemdf).

### <a name="example"></a>Örnek

  Aşağıdaki kod, *ProjName*App. cpp içine yerleştirilmelidir. Aşağıdaki genel değişkenleri tanımlayın:

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

İşlevinde şu `InitInstance` satırı ekleyin:

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

İşlev için bir işleyici ekleyin `ExitInstance` ve aşağıdaki kodu kullanın:

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

Artık işlevin çıkışını görmek için programı hata ayıklama modunda çalıştırabilirsiniz `DumpStatistics` .

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
