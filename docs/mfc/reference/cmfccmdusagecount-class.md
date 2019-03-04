---
title: CMFCCmdUsageCount sınıfı
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
ms.openlocfilehash: b4ad9a60831feb6fa1147ea3f8bcfd5c6badd06c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275369"
---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount sınıfı

Windows iletileri, kullanıcı bir menüden bir öğe seçtiğinde gibi kullanım sayısını izler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCCmdUsageCount : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Ad|Açıklama|
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Varsayılan Oluşturucu.|
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CMFCCmdUsageCount::AddCmd](#addcmd)|Bir verilen komutu ile ilişkili olan sayaç artırır.|
|[CMFCCmdUsageCount::GetCount](#getcount)|Belirtilen komut kimliğiyle ilişkili kullanım sayısını alır.|
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|Bu nesne minimum izleme verileri miktarını toplanan olup olmadığını belirler.|
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|Verilen komutu sık kullanılıp kullanılmayacağını belirler.|
|[CMFCCmdUsageCount::Reset](#reset)|Tüm komutlar kullanım sayısı temizler.|
|[CMFCCmdUsageCount::Serialize](#serialize)|Bu nesne bir arşivden okur veya arşive yazar. (Geçersiz kılmaları [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|
|[CMFCCmdUsageCount::SetOptions](#setoptions)|Kümeleri değerlerini paylaşılan `CMFCCmdUsageCount` sınıf veri üyeleri.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|Ad|Açıklama|
|`m_CmdUsage`|A `CMap` komutları için kendi kullanım sayıları eşleyen nesne.|
|`m_nMinUsagePercentage`|Sık kullanılan bir komut için en az kullanım yüzdesi.|
|`m_nStartCount`|Bu nesne minimum izleme verileri miktarını toplanan olup olmadığını belirlemek için kullanılan başlangıç sayacı.|
|`m_nTotalUsage`|İzlenen tüm komutları sayısı.|

### <a name="remarks"></a>Açıklamalar

`CMFCCmdUsageCount` Sınıfı her sayısal Windows İleti tanımlayıcısı bir 32-bit işaretsiz tamsayı sayaç eşler. `CMFCToolBar` Sık kullanılan araç çubuğu öğelerini görüntülemek için bu sınıfı kullanır. Hakkında daha fazla bilgi için `CMFCToolBar`, bkz: [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md).

Kalıcı yapılabilir `CMFCCmdUsageCount` programınızın çalıştırmaları arasında veri sınıfı. Kullanım [CMFCCmdUsageCount::Serialize](#serialize) sınıf üye verileri seri hale getirmek için gereken yöntemini ve [CMFCCmdUsageCount::SetOptions](#setoptions) paylaşılan üye veri kümesi için yöntemi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmdusagecount.h

##  <a name="addcmd"></a>  CMFCCmdUsageCount::AddCmd

Bir verilen komutu ile ilişkili olan sayaç artırır.

```
void AddCmd(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*uiCmd*|[in] Artırılacak komut sayacı belirtir.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem yeni bir giriş komut sayıları harita yapısına ekler `m_CmdUsage`, girdisi zaten mevcut değilse.

Bu yöntem, aşağıdaki durumlarda bir şey yapar:

- Özelleştirme modu araç çubuğu çerçevedir ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) sıfır olmayan bir değer döndürür).

- Komut için bir alt menü veya menü ayırıcısını ifade eder ( *uiCmd* eşittir 0 veya -1).

- *uiCmd* için standart bir komut başvurur (genel `IsStandardCommand` işlevi sıfır olmayan bir değer döndürür).

##  <a name="getcount"></a>  CMFCCmdUsageCount::GetCount

Belirtilen komut kimliğiyle ilişkili kullanım sayısını alır.

```
UINT GetCount(UINT uiCmd) const;
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*uiCmd*|[in] Alınacak komut sayaç kimliği.|

### <a name="return-value"></a>Dönüş Değeri

Belirtilen komut kimliğiyle ilişkili kullanım sayısı

##  <a name="hasenoughinformation"></a>  CMFCCmdUsageCount::HasEnoughInformation

Bu nesne minimum izleme verileri miktarını aldı olup olmadığını belirler.

```
BOOL HasEnoughInformation() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne minimum izleme verileri miktarını aldı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, sıfır dışında bir değeri döndürür toplam sayısını `m_nTotalUsage`, izlenen tüm komutların ilk sayısından daha büyük veya eşit olan `m_nStartCount`. Varsayılan olarak, ilk sayısı 0 framework ayarlar. Kullanarak bu değeri geçersiz kılabilirsiniz [CMFCCmdUsageCount::SetOptions](#setoptions) yöntemi.

Bu yöntem tarafından kullanılan [CMFCMenuBar::IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) tüm kullanılabilir menü komutları görüntülenip görüntülenmeyeceğini belirlemek için.

##  <a name="isfreqeuntlyusedcmd"></a>  CMFCCmdUsageCount::IsFreqeuntlyUsedCmd

Verilen komutu sık kullanılıp kullanılmayacağını belirler.

```
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*uiCmd*|[in] Denetlemek için komutu belirtir.|

### <a name="return-value"></a>Dönüş Değeri

Komut sık kullanılan olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, 0 döndürür toplam komut kullanımı `m_nTotalUsage`, 0'dır. Aksi durumda bu yöntem belirtilen komut kullanılan yüzdeyi en düşük yüzdesini büyükse, sıfır döndürür `m_nMinUsagePercentage`. Varsayılan olarak, framework en az yüzde 5'e ayarlar. Kullanarak bu değeri geçersiz kılabilirsiniz [CMFCCmdUsageCount::SetOptions](#setoptions) yöntemi. En az yüzde 0 ise, bu yöntem, belirtilen komut sayısı 0'dan büyükse, sıfır döndürür.

[CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) komut nadiren kullanılıp kullanılmadığını belirlemek için bu yöntemi kullanır.

##  <a name="reset"></a>  CMFCCmdUsageCount::Reset

Tüm komutlar kullanım sayısı temizler.

```
void Reset();
```

### <a name="remarks"></a>Açıklamalar

Komut sayıları harita yapısını arasındaki tüm girişleri temizlemek için bu yöntemi çağırın `m_CmdUsage`, toplam komut kullanımı sıfırlamak için `m_nTotalUsage`, sayaç 0.

##  <a name="serialize"></a>  CMFCCmdUsageCount::Serialize

Bu nesne bir arşivden okur veya arşive yazar.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*ar*|[in] A `CArchive` veya seri hale getirmek için nesne.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem komut sayıları harita yapısını serileştiren `m_CmdUsage`ve toplam komut kullanım `m_nTotalUsage`, ya da belirtilen arşive sayaç.

Serileştirme örnekler için bkz [seri hale getirme: Bir nesneyi serileştirmek](../../mfc/serialization-serializing-an-object.md).

##  <a name="setoptions"></a>  CMFCCmdUsageCount::SetOptions

Kümeleri değerlerini paylaşılan `CMFCCmdUsageCount` sınıf veri üyeleri.

```
static BOOL __stdcall SetOptions(
    UINT nStartCount,
    UINT nMinUsagePercentage);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*nStartCount*|[in] İzlenen tüm komutların yeni ilk sayısı.|
|*nMinUsagePercentage*|[in] Yeni en az kullanım yüzdesi.|

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa, FALSE ise TRUE *nMinUsagePercentage* parametredir 100'değerine eşit veya daha büyük.

### <a name="remarks"></a>Açıklamalar

Bu yöntem paylaşılan ayarlar `CMFCCmdUsageCount` sınıf veri üyeleri `m_nStartCount` ve `m_nMinUsagePercentage` için *nStartCount* ve *nMinUsagePercentage*sırasıyla. `m_nStartCount` tarafından kullanılan [CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) bu nesne minimum izleme verileri miktarını toplanan olup olmadığını belirlemek için yöntemi. `m_nMinUsagePercentage` tarafından kullanılan [CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd) belirli bir komut sık kullanılıp kullanılmadığını belirlemek için yöntemi.

Hata ayıklama derlemelerinde, bu yöntem bir onaylama işlemi hatası oluşturur *nMinUsagePercentage* parametredir 100'değerine eşit veya daha büyük.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)
