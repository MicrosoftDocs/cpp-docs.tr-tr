---
title: CMFCCmdUsageCount Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
helpviewer_keywords:
- CMFCCmdUsageCount [MFC], AddCmd
- CMFCCmdUsageCount [MFC], GetCount
- CMFCCmdUsageCount [MFC], HasEnoughInformation
- CMFCCmdUsageCount [MFC], IsFreqeuntlyUsedCmd
- CMFCCmdUsageCount [MFC], Reset
- CMFCCmdUsageCount [MFC], Serialize
- CMFCCmdUsageCount [MFC], SetOptions
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
ms.openlocfilehash: 02b302ec38922128190a6f20ce2f156b52383b55
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752586"
---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount Sınıfı

Kullanıcı bir menüden öğe yi seçmesi gibi Windows iletilerinin kullanım sayısını izler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCCmdUsageCount : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Varsayılan oluşturucu.|
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCCmdKullanımCount::AddCmd](#addcmd)|Verilen komutla ilişkili sayaç tarafından artışlar.|
|[CMFCCmdKullanımCount::GetCount](#getcount)|Verilen komut kimliğiyle ilişkili kullanım sayısını alır.|
|[CMFCCmdKullanımCount::HasEnoughInformation](#hasenoughinformation)|Bu nesnenin en az izleme verisi toplayıp toplamadığını belirler.|
|[CMFCCmdKullanımCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|Verilen komutun sık kullanılıp kullanılmayacağını belirler.|
|[CMFCCmdKullanımCount::Sıfırla](#reset)|Tüm komutların kullanım sayısını temizler.|
|[CMFCCmdKullanımCount::Serialize](#serialize)|Bu nesneyi arşivden okur veya arşive yazar. (CObject geçersiz [kılar::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CMFCCmdKullanımCount::SetOptions](#setoptions)|Paylaşılan `CMFCCmdUsageCount` sınıf veri üyelerinin değerlerini ayarlar.|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|Adı|Açıklama|
|`m_CmdUsage`|Kullanımlarıyla komutları eşleyen bir `CMap` nesne sayar.|
|`m_nMinUsagePercentage`|Bir komutun sık kullanılması için minimum kullanım yüzdesi.|
|`m_nStartCount`|Bu nesnenin en az izleme verisi toplayıp toplamadığını belirlemek için kullanılan başlangıç sayacı.|
|`m_nTotalUsage`|İzlenen tüm komutların sayısı.|

### <a name="remarks"></a>Açıklamalar

Sınıf, `CMFCCmdUsageCount` her sayısal Windows ileti tanımlayıcısını 32 bit imzasız tamsayı sayacıyla eşler. `CMFCToolBar`sık kullanılan araç çubuğu öğelerini görüntülemek için bu sınıfı kullanır. Hakkında `CMFCToolBar`daha fazla bilgi için [CMFCToolBar Class'a](../../mfc/reference/cmfctoolbar-class.md)bakın.

Programınızın `CMFCCmdUsageCount` çalıştırmaları arasında sınıf verilerini devam ettirebilirsiniz. [CmFCCmdUsageCount kullanın::Sınıf](#serialize) üye verilerini serileştirmek için serialize yöntemini ve paylaşılan üye verilerini ayarlamak için [CMFCCmdUsageCount::SetOptions](#setoptions) yöntemini kullanın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCCmdKullanımSayısı](../../mfc/reference/cmfccmdusagecount-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmdusagecount.h

## <a name="cmfccmdusagecountaddcmd"></a><a name="addcmd"></a>CMFCCmdKullanımCount::AddCmd

Verilen komutla ilişkili sayaç tarafından artışlar.

```cpp
void AddCmd(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*uiCmd*|[içinde] Artış için komut sayacı belirtir.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, giriş zaten yoksa komut `m_CmdUsage`sayımlarının eşyapıyapısına yeni bir giriş ekler.

Bu yöntem aşağıdaki durumlarda hiçbir şey yapmaz:

- Araç çubuğu çerçevesi özelleştirme modundadır [(CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) yöntemi sıfır olmayan bir değer döndürür).

- Komut bir alt menü veya menü ayırıcı *(uiCmd* eşittir 0 veya -1) anlamına gelir.

- *uiCmd* standart bir komut (global `IsStandardCommand` işlev sıfır olmayan bir değer döndürür) anlamına gelir.

## <a name="cmfccmdusagecountgetcount"></a><a name="getcount"></a>CMFCCmdKullanımCount::GetCount

Verilen komut kimliğiyle ilişkili kullanım sayısını alır.

```
UINT GetCount(UINT uiCmd) const;
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*uiCmd*|[içinde] Alınacak komut sayacının kimliği.|

### <a name="return-value"></a>Dönüş Değeri

Verilen komut kimliğiyle ilişkili kullanım sayısı.

## <a name="cmfccmdusagecounthasenoughinformation"></a><a name="hasenoughinformation"></a>CMFCCmdKullanımCount::HasEnoughInformation

Bu nesnenin en az izleme verisi alıp almadığını belirler.

```
BOOL HasEnoughInformation() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne en az izleme verisi miktarı almışsa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İzlenen tüm komutların toplam sayısı `m_nTotalUsage`ilk sayıma eşit veya daha büyükse, `m_nStartCount`bu yöntem sıfır olmayan bir değer döndürür. Varsayılan olarak, çerçeve ilk sayı 0'ı ayarlar. [CMFCCmdUsageCount::SetOptions](#setoptions) yöntemini kullanarak bu değeri geçersiz kılabilirsiniz.

Bu yöntem CMFCMenuBar tarafından kullanılır::Tüm kullanılabilir menü komutları göstermek için olup olmadığını belirlemek için [IsShowAllCommands.](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands)

## <a name="cmfccmdusagecountisfreqeuntlyusedcmd"></a><a name="isfreqeuntlyusedcmd"></a>CMFCCmdKullanımCount::IsFreqeuntlyUsedCmd

Verilen komutun sık kullanılıp kullanılmayacağını belirler.

```
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*uiCmd*|[içinde] Denetlemek için komut belirtir.|

### <a name="return-value"></a>Dönüş Değeri

Komut sık kullanılırsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, toplam komut kullanımı `m_nTotalUsage`0 ise 0 döndürür. Aksi takdirde, belirtilen komutun kullanıldığı yüzde minimum yüzdeden daha büyükse, `m_nMinUsagePercentage`bu yöntem sıfırsız döndürür. Varsayılan olarak, çerçeve en az yüzdeyi 5 olarak ayarlar. [CMFCCmdUsageCount::SetOptions](#setoptions) yöntemini kullanarak bu değeri geçersiz kılabilirsiniz. Minimum yüzde 0 ise, belirtilen komut sayısı 0'dan büyükse bu yöntem sıfırsız döndürür.

[CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) bir komut nadiren kullanılıp kullanılmadığını belirlemek için bu yöntemi kullanır.

## <a name="cmfccmdusagecountreset"></a><a name="reset"></a>CMFCCmdKullanımCount::Sıfırla

Tüm komutların kullanım sayısını temizler.

```cpp
void Reset();
```

### <a name="remarks"></a>Açıklamalar

Komut sayımlarının `m_CmdUsage`harita yapısındaki tüm girişleri temizlemek ve toplam komut kullanımını `m_nTotalUsage`sıfırlamak için bu yöntemi 0'a çağırın.

## <a name="cmfccmdusagecountserialize"></a><a name="serialize"></a>CMFCCmdKullanımCount::Serialize

Bu nesneyi arşivden okur veya arşive yazar.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*Ar*|[içinde] Serihale `CArchive` veya için bir nesne.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `m_CmdUsage`komut sayımlarının eşyapısını ve belirtilen arşivden `m_nTotalUsage`gelen veya gelen toplam komut kullanımını serileştirir.

Serileştirme örnekleri için bkz: [Serileştirme: Nesneyi Serileştirme](../../mfc/serialization-serializing-an-object.md).

## <a name="cmfccmdusagecountsetoptions"></a><a name="setoptions"></a>CMFCCmdKullanımCount::SetOptions

Paylaşılan `CMFCCmdUsageCount` sınıf veri üyelerinin değerlerini ayarlar.

```
static BOOL __stdcall SetOptions(
    UINT nStartCount,
    UINT nMinUsagePercentage);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*nBaşlangıç Sayısı*|[içinde] İzlenen tüm komutların yeni ilk sayısı.|
|*nMinKullanımYüzdesi*|[içinde] Yeni minimum kullanım yüzdesi.|

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa DOĞRU, *nMinKullanımPercentage* parametresi 100'den büyük veya eşitse FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CMFCCmdUsageCount` paylaşılan sınıf `m_nStartCount` `m_nMinUsagePercentage` veri üyelerini ve sırasıyla *nStartCount* ve *nMinUsagePercentage'e*ayarlar. `m_nStartCount`[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) yöntemi tarafından bu nesnenin minimum izleme verisi miktarını toplayıp toplamadığını belirlemek için kullanılır. `m_nMinUsagePercentage`[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd) yöntemi ile belirli bir komutun sık kullanılıp kullanılmadığını belirlemek için kullanılır.

Hata Ayıklama oluştururda bu *yöntem, nMinKullanımPercentage* parametresi 100'den büyük veya eşitse bir sınayıcı hatası oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)
