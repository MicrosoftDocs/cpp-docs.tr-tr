---
title: CMemoryState yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMemoryState
dev_langs:
- C++
helpviewer_keywords:
- CMemoryState structure [MFC]
- memory leaks [MFC], detecting
- detecting memory leaks [MFC]
ms.assetid: 229d9de7-a6f3-4cc6-805b-5a9d9b1bfe1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba1d156d9453cd6a74a3543295d9d90d761e77f9
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040754"
---
# <a name="cmemorystate-structure"></a>CMemoryState yapısı
Bellek sızıntıları programınıza algılamak için kolay bir yol sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CMemoryState  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMemoryState::CMemoryState](#cmemorystate)|Bellek kontrol noktaları denetleyen bir sınıf benzeri yapısı oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMemoryState::Checkpoint](#checkpoint)|Geçerli bellek durumunun anlık görüntüsü (Denetim) alır.|  
|[CMemoryState::Difference](#difference)|İki nesne türü arasındaki farkı hesaplar `CMemoryState`.|  
|[CMemoryState::DumpAllObjectsSince](#dumpallobjectssince)|Tüm geçerli ayrılmış nesneleri özetini itibaren önceki bir denetim noktası dökümünü yapar.|  
|[CMemoryState::DumpStatistics](#dumpstatistics)|Bellek ayırma istatistiklerini yazdırır bir `CMemoryState` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMemoryState` bir yapıdır ve bir taban sınıfı yok.  
  
 Bir nesne için bellek ve yığında ayrılan ancak artık gerekli olmadığında serbest değil "Bellek sızıntısı" oluşuyor. Bu tür bellek sızıntıları sonunda bellek yetersiz hatalara yol açabilir. Ayırmak ve programınızdaki bellek ayırması için birkaç yolu vardır:  
  
-   Kullanarak `malloc` /  **ücretsiz** ailesi işlevlerini çalışma zamanı kitaplığı.  
  
-   Windows API bellek yönetimi işlevleri kullanarak **LocalAlloc**/ **LocalFree** ve **GlobalAlloc**/ **GlobalFree** .  
  
-   C++ kullanarak **yeni** ve **silmek** işleçler.  
  
 `CMemoryState` Tanılama yalnızca bellek belirlenmesine yardımcı kullanarak bellek tahsis ortaya sızıntıları **yeni** işleci değil serbest kullanarak **silmek**. Diğer iki bellek yönetimi işlevleri C++ dışı programları ve bunlarla karıştırma gruplarıdır **yeni** ve **silmek** aynı programda önerilmez. Bir ek makrosu `DEBUG_NEW`, değiştirmek için sağlanan **yeni** dosya ve satır numarası izleme bellek ayırmaları gerektiğinde işleci. `DEBUG_NEW` Normal olarak kullanacağınız her kullanılan **yeni** işleci.  
  
 Diğer bir tanılama olduğu gibi ile `CMemoryState` tanılama bulunan ve yalnızca programınızı hata ayıklama sürümleri. Hata ayıklama sürümü yüklü olmalıdır **_DEBUG** tanımlanan sabiti.  
  
 Programınızı sahip bir bellek sızıntısı şüpheleniyorsanız, kullanabileceğiniz `Checkpoint`, `Difference`, ve `DumpStatistics` işlevleri program yürütme iki farklı noktalarda bellek durumu (ayrılmış nesneler) arasındaki farkı bulur. Bu bilgiler bir işlev ayırdığı tüm nesneleri temizleme olup olmadığını belirlerken yararlı olabilir.  
  
 Yalnızca ayırma ve ayırmayı kaldırma dengesizliği nerede oluştuğunu bilmek yeterli bilgi sağlamıyorsa kullanabileceğiniz `DumpAllObjectsSince` önceki çağrısından itibaren ayrılan tüm nesneleri dökümü işlevi `Checkpoint`. Bu döküm ayırma, kaynak dosya ve nesne tahsis edildiğinde nerede satır sırasını gösterir (kullanıyorsanız `DEBUG_NEW` ayırma için) ve nesne, adresini ve boyutuna türevi. `DumpAllObjectsSince` Ayrıca her nesnenin çağırır `Dump` işlevi geçerli durumu hakkında bilgi sağlar.  
  
 Nasıl kullanılacağı hakkında daha fazla bilgi için `CMemoryState` ve diğer tanılama Bkz [hata ayıklama MFC uygulamaları](/visualstudio/debugger/mfc-debugging-techniques).  
  
> [!NOTE]
>  Nesne türü bildirimleri `CMemoryState` ve üye işlevleri çağrıları bracketed tarafından `#if defined(_DEBUG)/#endif` yönergeleri. Bu, yalnızca derlemeleri programınızın hata ayıklamaya dahil edilecek Bellek Tanılama neden olur.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CMemoryState`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afx.h  
  
##  <a name="checkpoint"></a>  CMemoryState::Checkpoint  
 Bir anlık görüntü bellek Özet alır ve bu depolar `CMemoryState` nesnesi.  
  
```  
void Checkpoint();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CMemoryState` Üye işlevleri [fark](#difference) ve [DumpAllObjectsSince](#dumpallobjectssince) bu anlık görüntü verileri kullanın.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMemoryState](#cmemorystate) Oluşturucusu.  
  
##  <a name="cmemorystate"></a>  CMemoryState::CMemoryState  
 Boş bir yapıları `CMemoryState` tarafından doldurulmalıdır nesne [denetim noktası](#checkpoint) veya [fark](#difference) üye işlevi.  
  
```  
CMemoryState();
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#18](../../mfc/codesnippet/cpp/cmemorystate-structure_1.cpp)]  
  
##  <a name="difference"></a>  CMemoryState::Difference  
 İki karşılaştırır `CMemoryState` nesneleri, sonra bu içine fark depolar `CMemoryState` nesnesi.  
  
```  
BOOL Difference(
    const CMemoryState& oldState,   
    const CMemoryState& newState);
```  
  
### <a name="parameters"></a>Parametreler  
 *oldState*  
 İlk bellek durumu tarafından tanımlandığı şekilde bir `CMemoryState` denetim noktası.  
  
 *newState*  
 Yeni bellek durumu tarafından tanımlanan bir `CMemoryState` denetim noktası.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İki bellek durumları farklıysa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 [Denetim noktası](#checkpoint) her iki bellek durumu parametreleri için çağrılmış gerekir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMemoryState](#cmemorystate) Oluşturucusu.  
  
##  <a name="dumpallobjectssince"></a>  CMemoryState::DumpAllObjectsSince  
 Çağrıları `Dump` işlevi bir türdeki tüm nesneleri için sınıfından türetilen `CObject` ayrılan (ve hala ayrılır) son [denetim noktası](#checkpoint) çağırmak için bu `CMemoryState` nesnesi.  
  
```  
void DumpAllObjectsSince() const;

 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırma `DumpAllObjectsSince` bir başlatılmamış ile `CMemoryState` nesne bellekte bulunan tüm nesneleri dökümü.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMemoryState](#cmemorystate) Oluşturucusu.  
  
##  <a name="dumpstatistics"></a>  CMemoryState::DumpStatistics  
 Kısa bellek istatistikleri rapordan yazdırır bir `CMemoryState` tarafından girilir nesne [fark](#difference) üye işlevi.  
  
```  
void DumpStatistics() const;

 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yazdırılır rapor [afxDump](diagnostic-services.md#afxdump) aygıt, şunları gösterir:  
  
 Örnek rapor numarası (veya tutar) hakkında bilgi verir:  
  
-   Ücretsiz blokları  
  
-   Normal blokları  
  
-   CRT blokları  
  
-   blokları yoksay  
  
-   istemci blokları  
  
-   Maksimum bellek (bayt cinsinden) herhangi bir zamanda program tarafından kullanılan  
  
-   şu anda program (bayt cinsinden) tarafından kullanılan toplam bellek  
  
 Ücretsiz taşlarıdır varsa, ayırmayı kaldırma gecikti blok sayısı `afxMemDF` ayarlandı **delayFreeMemDF**. Daha fazla bilgi için bkz: [afxMemDF](diagnostic-services.md#afxmemdf), "MFC makroları ve genel öğeleri" bölümünde. Bkz: [hata ayıklama yığınındaki blokları türleri](http://msdn.microsoft.com/en-us/db2e7f62-0679-4b39-a23f-26f2c2f407c5) bunlar hakkında daha fazla bilgi bloğu için türleri.  
  
### <a name="example"></a>Örnek  
  Aşağıdaki kod yerleştirilmelidir *projname*App.cpp. Aşağıdaki genel değişkenleri tanımlayın:  
  
 [!code-cpp[NVC_MFC_Utilities#40](../../mfc/codesnippet/cpp/cmemorystate-structure_2.cpp)]  
  
 İçinde `InitInstance` işlev, satırı ekleyin:  
  
 [!code-cpp[NVC_MFC_Utilities#41](../../mfc/codesnippet/cpp/cmemorystate-structure_3.cpp)]  
  
 İçin bir işleyici ekleyin `ExitInstance` işlev ve aşağıdaki kodu kullanabilirsiniz:  
  
 [!code-cpp[NVC_MFC_Utilities#42](../../mfc/codesnippet/cpp/cmemorystate-structure_4.cpp)]  
  
 Çıkışı görmek için hata ayıklama modunda şimdi program çalışabilir `DumpStatistics` işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



