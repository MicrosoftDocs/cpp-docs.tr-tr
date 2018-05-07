---
title: CMFCCmdUsageCount sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCCmdUsageCount [MFC], AddCmd
- CMFCCmdUsageCount [MFC], GetCount
- CMFCCmdUsageCount [MFC], HasEnoughInformation
- CMFCCmdUsageCount [MFC], IsFreqeuntlyUsedCmd
- CMFCCmdUsageCount [MFC], Reset
- CMFCCmdUsageCount [MFC], Serialize
- CMFCCmdUsageCount [MFC], SetOptions
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5b4824632d7ce38e50859172a24a47bdeb49f1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCCmdUsageCount::AddCmd](#addcmd)|Bir verilen komutla ilişkili sayaç artırır.|  
|[CMFCCmdUsageCount::GetCount](#getcount)|Verilen komut kimliğiyle ilişkili kullanım sayısını alır.|  
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|Bu nesne izleme verilerini minimum miktarını topladı olup olmadığını belirler.|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|Verilen komut sık kullanılan olup olmadığını belirler.|  
|[CMFCCmdUsageCount::Reset](#reset)|Tüm komutları kullanım sayısı temizler.|  
|[CMFCCmdUsageCount::Serialize](#serialize)|Bu nesne arşivden okur veya arşive yazar. (Geçersiz kılmaları [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CMFCCmdUsageCount::SetOptions](#setoptions)|Ayarlar değerlerini paylaşılan `CMFCCmdUsageCount` sınıfı veri üyesi.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`m_CmdUsage`|A `CMap` komutlar kendi kullanım sayıları eşlemeleri nesnesi.|  
|`m_nMinUsagePercentage`|Sık kullanılan bir komut için en düşük kullanım yüzdesi.|  
|`m_nStartCount`|Bu nesne izleme verilerini minimum miktarını topladı olup olmadığını belirlemek için kullanılan başlangıç sayacı.|  
|`m_nTotalUsage`|Tüm izlenen komutları sayısı.|  
  
### <a name="remarks"></a>Açıklamalar  
 `CMFCCmdUsageCount` Sınıfı bir 32 bit işaretsiz tamsayıyı sayaç her sayısal Windows İleti tanımlayıcısı eşler. `CMFCToolBar` Sık kullanılan araç çubuğu öğeleri görüntülemek için bu sınıfı kullanır. Hakkında daha fazla bilgi için `CMFCToolBar`, bkz: [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md).  
  
 Devam edebilir `CMFCCmdUsageCount` sınıf programınızın çalıştırmaları arasında veri. Kullanım [CMFCCmdUsageCount::Serialize](#serialize) sınıf üye verileri seri hale getirmek için yöntem ve [CMFCCmdUsageCount::SetOptions](#setoptions) paylaştırılmış üye veri kümesi için yöntem.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmdusagecount.h  
  
##  <a name="addcmd"></a>  CMFCCmdUsageCount::AddCmd  
 Bir verilen komutla ilişkili sayaç artırır.  
  
```  
void AddCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] `uiCmd`|Artırmak için komut sayaç belirtir.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yeni bir giriş komutu sayımları harita yapısını ekler `m_CmdUsage`, giriş zaten mevcut değilse.  
  
 Bu yöntem aşağıdaki durumlarda hiçbir şey yapmaz:  
  
-   Araç çubuğu framework özelleştirme modundayken ( [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) yöntemi sıfır olmayan bir değer döndürür).  
  
-   Komut bir alt menü veya menü ayırıcı ifade eder ( `uiCmd` eşittir 0 veya -1).  
  
- `uiCmd` Standart komut ifade eder (genel `IsStandardCommand` işlevi sıfır olmayan bir değer döndürür).  
  
##  <a name="getcount"></a>  CMFCCmdUsageCount::GetCount  
 Verilen komut kimliğiyle ilişkili kullanım sayısını alır.  
  
```  
UINT GetCount(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] `uiCmd`|Almak üzere komut sayaç kimliği.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen komut kimliğiyle ilişkili kullanımı sayısı  
  
##  <a name="hasenoughinformation"></a>  CMFCCmdUsageCount::HasEnoughInformation  
 Bu nesne izleme verilerini minimum miktarını aldı olup olmadığını belirler.  
  
```  
BOOL HasEnoughInformation() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu nesne izleme verilerini minimum miktarını aldıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, sıfır olmayan bir değer döndürür toplam sayısı `m_nTotalUsage`, tüm izlenen komutlarını eşit veya ilk sayısından daha büyük olan `m_nStartCount`. Varsayılan olarak, ilk sayısı 0 framework ayarlar. Kullanarak bu değeri geçersiz kılabilirsiniz [CMFCCmdUsageCount::SetOptions](#setoptions) yöntemi.  
  
 Bu yöntem tarafından kullanılan [CMFCMenuBar::IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) tüm kullanılabilir menü komutlarını gösterilip gösterilmeyeceğini belirlemek için.  
  
##  <a name="isfreqeuntlyusedcmd"></a>  CMFCCmdUsageCount::IsFreqeuntlyUsedCmd  
 Verilen komut sık kullanılan olup olmadığını belirler.  
  
```  
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] `uiCmd`|Denetlemek için komutu belirtir.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Komutu sık kullanılması halinde sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem 0 döndürür toplam komutu kullanım `m_nTotalUsage`, 0'dır. Aksi takdirde, bu yöntem belirtilen komutu kullanılan yüzde en düşük yüzdesini büyükse, sıfır olmayan döndürür `m_nMinUsagePercentage`. Varsayılan olarak, framework en az yüzde 5'e ayarlar. Kullanarak bu değeri geçersiz kılabilirsiniz [CMFCCmdUsageCount::SetOptions](#setoptions) yöntemi. En az yüzde 0 ise, bu yöntem belirtilen komut sayısı 0'dan büyükse, sıfır olmayan bir değer döndürür.  
  
 [CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) komut nadiren kullanılır olup olmadığını belirlemek için bu yöntemi kullanır.  
  
##  <a name="reset"></a>  CMFCCmdUsageCount::Reset  
 Tüm komutları kullanım sayısı temizler.  
  
```  
void Reset();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Komutu sayımları harita yapısını tüm girişleri temizlemek için bu yöntemi çağırın `m_CmdUsage`, toplam komutu kullanım sıfırlamak için `m_nTotalUsage`, 0 sayaç.  
  
##  <a name="serialize"></a>  CMFCCmdUsageCount::Serialize  
 Bu nesne arşivden okur veya arşive yazar.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] `ar`|A `CArchive` veya seri hale getirmek için nesne.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem komutu sayımları harita yapısını serileştiren `m_CmdUsage`ve toplam komutu kullanım `m_nTotalUsage`, ya da belirtilen arşive sayaç.  
  
 Seri hale getirme örnekler için bkz: [seri hale getirme: bir nesneyi seri hale getirme](../../mfc/serialization-serializing-an-object.md).  
  
##  <a name="setoptions"></a>  CMFCCmdUsageCount::SetOptions  
 Ayarlar değerlerini paylaşılan `CMFCCmdUsageCount` sınıfı veri üyesi.  
  
```  
static BOOL __stdcall SetOptions(
    UINT nStartCount,  
    UINT nMinUsagePercentage);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] `nStartCount`|Tüm izlenen komutları yeni ilk sayısı.|  
|[in] `nMinUsagePercentage`|Yeni minimum kullanım yüzdesi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` yöntem başarılı olursa, `FALSE` varsa `nMinUsagePercentage` parametredir 100'değerine eşit veya daha büyük.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem paylaşılan ayarlar `CMFCCmdUsageCount` sınıfı veri üyesi `m_nStartCount` ve `m_nMinUsagePercentage` için `nStartCount` ve `nMinUsagePercentage`sırasıyla. `m_nStartCount` tarafından kullanılan [CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) bu nesne izleme verilerini minimum miktarını topladı olup olmadığını belirlemek amacıyla yöntemi. `m_nMinUsagePercentage` tarafından kullanılan [CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd) verilen komut sık kullanılan olup olmadığını belirlemek amacıyla yöntemi.  
  
 Hata ayıklama derlemelerinde, bu yöntem bir onaylama işlemi hatasına oluşturur `nMinUsagePercentage` parametredir 100'değerine eşit veya daha büyük.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)
