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
ms.openlocfilehash: 95dca548856510cd8b06914932cc46435c28399d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834283"
---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount sınıfı

Kullanıcının menüden bir öğe seçtiği zaman gibi Windows iletilerinin kullanım sayısını izler.

## <a name="syntax"></a>Syntax

```
class CMFCCmdUsageCount : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|-|-|
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Varsayılan Oluşturucu.|
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|-|-|
|[CMFCCmdUsageCount:: AddCmd](#addcmd)|Verilen komutla ilişkili bir sayaca göre artar.|
|[CMFCCmdUsageCount:: GetCount](#getcount)|Verilen komut KIMLIĞIYLE ilişkili kullanım sayısını alır.|
|[CMFCCmdUsageCount:: HasEnoughInformation](#hasenoughinformation)|Bu nesnenin minimum izleme verisi miktarını topladığını belirler.|
|[CMFCCmdUsageCount:: ıfreqeuntlyusedcmd](#isfreqeuntlyusedcmd)|Verilen komutun sık kullanılıp kullanılmadığını belirler.|
|[CMFCCmdUsageCount:: Reset](#reset)|Tüm komutların kullanım sayısını temizler.|
|[CMFCCmdUsageCount:: serileştirme](#serialize)|Bu nesneyi bir arşivden okur veya bir arşive yazar. ( [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize)geçersiz kılar.)|
|[CMFCCmdUsageCount:: SetOptions](#setoptions)|Paylaşılan `CMFCCmdUsageCount` sınıf veri üyelerinin değerlerini ayarlar.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|-|-|
|`m_CmdUsage`|`CMap`Komutları kullanım sayılarıyla eşleyen bir nesne.|
|`m_nMinUsagePercentage`|Bir komut için sık kullanılan en düşük kullanım yüzdesi.|
|`m_nStartCount`|Bu nesnenin en düşük izleme verisi miktarını topladığını belirlemede kullanılan başlangıç sayacı.|
|`m_nTotalUsage`|İzlenen tüm komutların sayısı.|

### <a name="remarks"></a>Açıklamalar

`CMFCCmdUsageCount`Sınıfı her bir sayısal Windows ileti tanımlayıcısını 32 bitlik işaretsiz bir tamsayı sayaca eşler. `CMFCToolBar` sık kullanılan araç çubuğu öğelerini göstermek için bu sınıfı kullanır. Hakkında daha fazla bilgi için `CMFCToolBar` bkz. [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md).

`CMFCCmdUsageCount`Programınızın çalıştırmaları arasında sınıf verilerini kalıcı hale getirebilirsiniz. Paylaşılan üye verilerini ayarlamak için, sınıf üyesi verilerini ve [CMFCCmdUsageCount:: SetOptions](#setoptions) metodunu seri hale getirmek Için [CMFCCmdUsageCount:: Serialize](#serialize) metodunu kullanın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmdusagecount. h

## <a name="cmfccmdusagecountaddcmd"></a><a name="addcmd"></a> CMFCCmdUsageCount:: AddCmd

Verilen komutla ilişkili bir sayaca göre artar.

```cpp
void AddCmd(UINT uiCmd);
```

### <a name="parameters"></a>Parametreler

*Uımd*\
'ndaki Artıtacak komut sayacını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, giriş zaten yoksa, komut sayılarının harita yapısına yeni bir giriş ekler `m_CmdUsage` .

Bu yöntem, aşağıdaki durumlarda hiçbir şey yapmaz:

- Araç çubuğu çerçevesi özelleştirme modunda ( [CMFCToolBar:: IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) yöntemi sıfır dışında bir değer döndürür).

- Komut bir alt menüyü veya menü ayırıcısını ( *uiCmd* eşittir 0 veya-1) ifade eder.

- *Uıımd* standart bir komuta başvurur (genel `IsStandardCommand` işlev sıfır dışında bir değer döndürür).

## <a name="cmfccmdusagecountgetcount"></a><a name="getcount"></a> CMFCCmdUsageCount:: GetCount

Verilen komut KIMLIĞIYLE ilişkili kullanım sayısını alır.

```
UINT GetCount(UINT uiCmd) const;
```

### <a name="parameters"></a>Parametreler

*Uımd*\
'ndaki Alınacak komut sayacının KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Verilen komut KIMLIĞIYLE ilişkili kullanım sayısı.

## <a name="cmfccmdusagecounthasenoughinformation"></a><a name="hasenoughinformation"></a> CMFCCmdUsageCount:: HasEnoughInformation

Bu nesnenin minimum izleme verisi miktarını aldığını belirler.

```
BOOL HasEnoughInformation() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne en az izleme verisi miktarı aldıysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `m_nTotalUsage` tüm izlenen komutların toplam sayısı, ilk sayımla eşit veya daha büyük olduğunda, sıfır dışında bir değer döndürür `m_nStartCount` . Varsayılan olarak, çerçeve ilk sayıyı 0 olarak ayarlar. Bu değeri [CMFCCmdUsageCount:: SetOptions](#setoptions) metodunu kullanarak geçersiz kılabilirsiniz.

Bu yöntem, tüm kullanılabilir menü komutlarının gösterilip gösterilmeyeceğini belirlemede [CMFCMenuBar:: IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) tarafından kullanılır.

## <a name="cmfccmdusagecountisfreqeuntlyusedcmd"></a><a name="isfreqeuntlyusedcmd"></a> CMFCCmdUsageCount:: ıfreqeuntlyusedcmd

Verilen komutun sık kullanılıp kullanılmadığını belirler.

```
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;
```

### <a name="parameters"></a>Parametreler

*Uımd*\
'ndaki Denetlenecek komutu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Komut sık sık kullanılıyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Toplam komut kullanımı 0 ise, bu yöntem 0 döndürür `m_nTotalUsage` . Aksi halde, belirtilen komutun kullanılma yüzdesi en düşük yüzdeden daha büyükse bu yöntem sıfır dışında bir değer döndürür `m_nMinUsagePercentage` . Varsayılan olarak, çerçeve en düşük yüzdeyi 5 olarak ayarlar. Bu değeri [CMFCCmdUsageCount:: SetOptions](#setoptions) metodunu kullanarak geçersiz kılabilirsiniz. Minimum yüzde 0 ise, belirtilen komut sayısı 0 ' dan büyükse bu yöntem sıfır dışında bir değer döndürür.

[CMFCToolBar:: ıscommandrarelykullanılma](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) , bir komutun nadiren kullanılıp kullanılmadığını anlamak için bu yöntemi kullanır.

## <a name="cmfccmdusagecountreset"></a><a name="reset"></a> CMFCCmdUsageCount:: Reset

Tüm komutların kullanım sayısını temizler.

```cpp
void Reset();
```

### <a name="remarks"></a>Açıklamalar

Komut sayımlarının harita yapısındaki tüm girişleri temizlemek `m_CmdUsage` ve toplam komut kullanımını, sayacı 0 olarak sıfırlamak için bu yöntemi çağırın `m_nTotalUsage` .

## <a name="cmfccmdusagecountserialize"></a><a name="serialize"></a> CMFCCmdUsageCount:: serileştirme

Bu nesneyi bir arşivden okur veya bir arşive yazar.

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*\
'ndaki `CArchive` Veya ile seri hale getirilecek bir nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut sayılarının eşleme yapısını, `m_CmdUsage` ve toplam komut kullanımı, `m_nTotalUsage` , sayacını veya belirtilen arşivden seri hale getirir.

Serileştirme örnekleri için bkz. [serileştirme: nesne serileştirmesi](../../mfc/serialization-serializing-an-object.md).

## <a name="cmfccmdusagecountsetoptions"></a><a name="setoptions"></a> CMFCCmdUsageCount:: SetOptions

Paylaşılan `CMFCCmdUsageCount` sınıf veri üyelerinin değerlerini ayarlar.

```
static BOOL __stdcall SetOptions(
    UINT nStartCount,
    UINT nMinUsagePercentage);
```

### <a name="parameters"></a>Parametreler

*nStartCount*\
'ndaki İzlenen tüm komutların yeni ilk sayısı.

*nMinUsagePercentage*\
'ndaki Yeni minimum kullanım yüzdesi.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE, *nMinUsagePercentage* parametresi 100 değerinden büyük veya bu değere eşitse false.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, paylaşılan `CMFCCmdUsageCount` sınıf veri üyelerini `m_nStartCount` ve `m_nMinUsagePercentage` sırasıyla *nStartCount* ve *nMinUsagePercentage*öğesini ayarlar. `m_nStartCount` , bu nesnenin en az izleme verisi miktarını topladığını tespit etmek için [CMFCCmdUsageCount:: HasEnoughInformation](#hasenoughinformation) yöntemi tarafından kullanılır. `m_nMinUsagePercentage` , belirli bir komutun sık sık kullanılıp kullanılmadığını anlamak için [CMFCCmdUsageCount:: ıfreqeuntlyusedcmd](#isfreqeuntlyusedcmd) yöntemi tarafından kullanılır.

Hata ayıklama Derlemeleriyle, *nMinUsagePercentage* parametresi 100 değerinden büyük veya bu değere eşitse bir onaylama hatası oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)
