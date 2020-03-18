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
ms.openlocfilehash: a110e1345cb970c117de125bd8105e1bc86eaf94
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79420689"
---
# <a name="cmemorystate-structure"></a>CMemoryState yapısı

Programınızdaki bellek sızıntılarını algılamaya yönelik kolay bir yol sağlar.

## <a name="syntax"></a>Sözdizimi

```
struct CMemoryState
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CMemoryState:: CMemoryState](#cmemorystate)|Bellek denetim noktalarını denetleyen sınıf benzeri bir yapı oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CMemoryState:: Checkpoint](#checkpoint)|Geçerli bellek durumunun anlık görüntüsünü (Checkpoint) alır.|
|[CMemoryState::D ifference](#difference)|`CMemoryState`türü iki nesne arasındaki farkı hesaplar.|
|[CMemoryState::D umpAllObjectsSince](#dumpallobjectssince)|Önceki bir kontrol noktasından bu yana, ayrılmış olan tüm nesnelerin özetini döker.|
|[CMemoryState::D öncelik Istatistikleri](#dumpstatistics)|`CMemoryState` nesne için bellek ayırma istatistiklerini yazdırır.|

## <a name="remarks"></a>Açıklamalar

`CMemoryState` bir yapıdır ve temel sınıfına sahip değildir.

Bir nesnenin belleği yığında ayrıldığında ancak artık gerekli olmadığında serbest bırakılmadığında "bellek sızıntısı" oluşur. Bu tür bellek sızıntıları sonunda bellek yetersiz hatalara neden olabilir. Programınızda bellek ayırmayı ve serbest bırakmak için çeşitli yollar vardır:

- Çalışma zamanı kitaplığındaki `malloc`/ `free` işlevlerini kullanma.

- Windows API bellek yönetimi işlevlerini kullanarak, `LocalAlloc`/ `LocalFree` ve `GlobalAlloc`/ `GlobalFree`.

- C++ **New** ve **Delete** işleçlerini kullanma.

`CMemoryState` tanılama, **Yeni** işleç kullanılarak ayrılan bellek, **silme**kullanılarak serbest bırakılmadığında, yalnızca bellek sızıntılarını algılamaya yardımcı olur. Diğer iki bellek yönetimi işlevleri,C++ programlar için değildir ve aynı programda **Yeni** ve **Sil** ile karıştırılması önerilmez. Ek bir makro DEBUG_NEW, bellek ayırmalarının dosya ve satır numarası izlemeye ihtiyacınız olduğunda **Yeni** işlecin yerine geçecek şekilde sağlanır. DEBUG_NEW, normalde **New** işlecini her kullandığınızda kullanılır.

Diğer tanılamalarda olduğu gibi `CMemoryState` tanılamayı yalnızca programınızın hata ayıklama sürümlerinde bulabilirsiniz. Hata ayıklama sürümünde _DEBUG sabit tanımlanmış olmalıdır.

Programınızın bellek sızıntısı olduğunu fark ediyorsanız, `Checkpoint`, `Difference`ve `DumpStatistics` işlevlerini kullanarak, program yürütmesindeki iki farklı noktada bellek durumu (ayrılan nesneler) arasındaki farkı bulabilirsiniz. Bu bilgiler, bir işlevin ayırdığı tüm nesneleri temizleyip temizedilmeyeceğini belirlemek için yararlı olabilir.

Ayırma ve ayırmayı kaldırma işleminin ne olduğunu bilmenin yeterli bilgi sağlamadığından, `DumpAllObjectsSince` işlevini kullanarak, önceki `Checkpoint`çağrısından bu yana ayrılan tüm nesnelerin dökümünü alabilirsiniz. Bu döküm, ayırmanın sırasını, kaynak dosyayı ve nesnenin ayrıldığı satırı (ayırma için DEBUG_NEW kullanıyorsanız), nesnenin elde edilmesini, adresini ve boyutunu gösterir. `DumpAllObjectsSince` Ayrıca her nesnenin `Dump` işlevini çağırarak geçerli durumu hakkında bilgi sağlar.

`CMemoryState` ve diğer tanılamayı kullanma hakkında daha fazla bilgi için bkz. [MFC uygulamalarında hata ayıklama](/visualstudio/debugger/mfc-debugging-techniques).

> [!NOTE]
>  `CMemoryState` türündeki nesnelerin bildirimleri ve üye işlevlerine yapılan çağrılar `#if defined(_DEBUG)/#endif` yönergeleriyle parantez içine alınmalıdır. Bu, bellek tanılamalarını yalnızca programınızın hata ayıklamasına dahil edilmesini sağlar.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CMemoryState`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AFX. h

##  <a name="checkpoint"></a>CMemoryState:: Checkpoint

Belleğin anlık görüntü özetini alır ve bu `CMemoryState` nesnesinde depolar.

```
void Checkpoint();
```

### <a name="remarks"></a>Açıklamalar

`CMemoryState` üye işlevleri [fark](#difference) ve [DumpAllObjectsSince](#dumpallobjectssince) bu anlık görüntü verilerini kullanır.

### <a name="example"></a>Örnek

  [CMemoryState](#cmemorystate) oluşturucusunun örneğine bakın.

##  <a name="cmemorystate"></a>CMemoryState:: CMemoryState

[Denetim noktası](#checkpoint) veya [fark](#difference) üye işlevi tarafından doldurulması gereken boş bir `CMemoryState` nesnesi oluşturur.

```
CMemoryState();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]

##  <a name="difference"></a>CMemoryState::D ifference

İki `CMemoryState` nesnesini karşılaştırır ve sonra farkı bu `CMemoryState` nesnesine depolar.

```
BOOL Difference(
    const CMemoryState& oldState,
    const CMemoryState& newState);
```

### <a name="parameters"></a>Parametreler

*Eski durum*<br/>
`CMemoryState` denetim noktası tarafından tanımlanan başlangıç belleği durumu.

*Yeni durum*<br/>
`CMemoryState` denetim noktası tarafından tanımlanan yeni bellek durumu.

### <a name="return-value"></a>Dönüş Değeri

İki bellek durumu farklıysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İki bellek durumu parametresi için [denetim noktası](#checkpoint) çağrılmalıdır.

### <a name="example"></a>Örnek

  [CMemoryState](#cmemorystate) oluşturucusunun örneğine bakın.

##  <a name="dumpallobjectssince"></a>CMemoryState::D umpAllObjectsSince

Bu `CMemoryState` nesnesinin son [denetim noktası](#checkpoint) çağrısından bu yana ayrılan (ve hala ayrılan) sınıf `CObject` türetilmiş bir türün tüm nesneleri için `Dump` işlevini çağırır.

```
void DumpAllObjectsSince() const;
```

### <a name="remarks"></a>Açıklamalar

Başlatılmamış bir `CMemoryState` nesnesiyle `DumpAllObjectsSince` çağırmak, şu anda bellekte bulunan tüm nesneleri dökümünü alacak.

### <a name="example"></a>Örnek

  [CMemoryState](#cmemorystate) oluşturucusunun örneğine bakın.

##  <a name="dumpstatistics"></a>CMemoryState::D öncelik Istatistikleri

[Fark](#difference) üye işlevi tarafından doldurulan bir `CMemoryState` nesnesinden kısa bir bellek istatistikleri raporu yazdırır.

```
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

Ücretsiz bloklar, `afxMemDF` `delayFreeMemDF`olarak ayarlandıysa, ayırmayı kaldırma geciktirilen blokların sayısıdır. Daha fazla bilgi için bkz. "MFC makroları ve genel" bölümünde [afxMemDF](diagnostic-services.md#afxmemdf).

### <a name="example"></a>Örnek

  Aşağıdaki kod, *ProjName*App. cpp içine yerleştirilmelidir. Aşağıdaki genel değişkenleri tanımlayın:

[!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]

`InitInstance` işlevinde şu satırı ekleyin:

[!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]

`ExitInstance` işlevi için bir işleyici ekleyin ve aşağıdaki kodu kullanın:

[!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]

Artık `DumpStatistics` işlevinin çıkışını görmek için programı hata ayıklama modunda çalıştırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
