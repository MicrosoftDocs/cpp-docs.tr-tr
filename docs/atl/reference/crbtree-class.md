---
title: CRBTree sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRBTree
- ATLCOLL/ATL::CRBTree
- ATLCOLL/ATL::CRBTree::KINARGTYPE
- ATLCOLL/ATL::CRBTree::KOUTARGTYPE
- ATLCOLL/ATL::CRBTree::VINARGTYPE
- ATLCOLL/ATL::CRBTree::VOUTARGTYPE
- ATLCOLL/ATL::CRBTree::FindFirstKeyAfter
- ATLCOLL/ATL::CRBTree::GetAt
- ATLCOLL/ATL::CRBTree::GetCount
- ATLCOLL/ATL::CRBTree::GetHeadPosition
- ATLCOLL/ATL::CRBTree::GetKeyAt
- ATLCOLL/ATL::CRBTree::GetNext
- ATLCOLL/ATL::CRBTree::GetNextAssoc
- ATLCOLL/ATL::CRBTree::GetNextKey
- ATLCOLL/ATL::CRBTree::GetNextValue
- ATLCOLL/ATL::CRBTree::GetPrev
- ATLCOLL/ATL::CRBTree::GetTailPosition
- ATLCOLL/ATL::CRBTree::GetValueAt
- ATLCOLL/ATL::CRBTree::IsEmpty
- ATLCOLL/ATL::CRBTree::RemoveAll
- ATLCOLL/ATL::CRBTree::RemoveAt
- ATLCOLL/ATL::CRBTree::SetValueAt
dev_langs:
- C++
helpviewer_keywords:
- CRBTree class
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b15ddf62545d5926faf75af760ed52219f1cb03
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="crbtree-class"></a>CRBTree sınıfı
Bu sınıf oluşturma ve kırmızı siyah ağaç kullanan yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>> 
class CRBTree
```  
  
#### <a name="parameters"></a>Parametreler  
 `K`  
 Anahtar öğe türü.  
  
 *V*  
 Değer öğe türü.  
  
 `KTraits`  
 Kopyalama veya anahtar öğeleri taşıma için kullanılan kod. Bkz: [CElementTraits sınıfı](../../atl/reference/celementtraits-class.md) daha fazla ayrıntı için.  
  
 `VTraits`  
 Kopyalama veya değer öğeleri taşıma için kullanılan kod.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRBTree::KINARGTYPE](#kinargtype)|Bir giriş bağımsız değişkeni bir anahtar geçirildiğinde kullanılan türü.|  
|[CRBTree::KOUTARGTYPE](#koutargtype)|Bir anahtar çıkış bağımsız değişken olarak döndürüldüğünde kullanılan türü.|  
|[CRBTree::VINARGTYPE](#vinargtype)|Bir giriş bağımsız değişkeni bir değer geçirildiğinde kullanılan türü.|  
|[CRBTree::VOUTARGTYPE](#voutargtype)|Çıkış bağımsız değişken olarak bir değer geçirildiğinde kullanılan türü.|  
  
### <a name="public-classes"></a>Genel sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRBTree::CPair sınıfı](#cpair_class)|Anahtar ve değer öğeleri içeren bir sınıf.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRBTree:: ~ CRBTree](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)|Sonraki kullanılabilir anahtar kullanan öğenin konumunu bulmak için bu yöntemi çağırın.|  
|[CRBTree::GetAt](#getat)|Ağacında verilen konumda öğesini almak için bu yöntemi çağırın.|  
|[CRBTree::GetCount](#getcount)|Öğe sayısını ağacında almak için bu yöntemi çağırın.|  
|[CRBTree::GetHeadPosition](#getheadposition)|Ağaç başındaki öğesi için konum değerini almak için bu yöntemi çağırın.|  
|[CRBTree::GetKeyAt](#getkeyat)|Ağacında belirli bir konumdan anahtarını almak için bu yöntemi çağırın.|  
|[CRBTree::GetNext](#getnext)|Depolanmış bir öğe için bir işaretçi elde etmek için bu yöntemi çağırın `CRBTree` nesne ve sonraki öğeye konumu ilerleyin.|  
|[CRBTree::GetNextAssoc](#getnextassoc)|Anahtar ve değer eşlemesinde depolanan bir öğenin almak için bu yöntemi çağırın ve sonraki öğeye konumu ilerleyin.|  
|[CRBTree::GetNextKey](#getnextkey)|Ağaçta depolanan bir öğenin anahtarı almak için bu yöntemi çağırın ve sonraki öğeye konumu ilerleyin.|  
|[CRBTree::GetNextValue](#getnextvalue)|Ağaçta depolanan bir öğe değerini almak için bu yöntemi çağırın ve sonraki öğeye konumu ilerleyin.|  
|[CRBTree::GetPrev](#getprev)|Depolanmış bir öğe için bir işaretçi elde etmek için bu yöntemi çağırın `CRBTree` nesnesi ve ardından önceki öğesine konumu güncelleştirin.|  
|[CRBTree::GetTailPosition](#gettailposition)|Ağaç kuyruğu öğede için konum değerini almak için bu yöntemi çağırın.|  
|[CRBTree::GetValueAt](#getvalueat)|Belirli bir konumda depolanan değerini almak için bu yöntemi çağırın `CRBTree` nesnesi.|  
|[CRBTree::IsEmpty](#isempty)|Bir boş ağaç nesne için test etmek için bu yöntemi çağırın.|  
|[CRBTree::RemoveAll](#removeall)|Tüm öğeleri kaldırmak için bu yöntemi çağırın **CRBTree** nesnesi.|  
|[CRBTree::RemoveAt](#removeat)|Belirtilen konumda öğesini kaldırmak için bu yöntemi çağırın **CRBTree** nesnesi.|  
|[CRBTree::SetValueAt](#setvalueat)|Belirli bir konumda depolanan değeri değiştirmek için bu yöntemi çağırın `CRBTree` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kırmızı siyah ağaç fazladan kullanan bir ikili arama ağacıdır bit onu kalmasını sağlamak için düğüm başına bilgilerinin "Dengeli," olan, ağaç yüksekliğini orantısız büyük büyür ve performansı etkileyen değil.  
  
 Bu şablon sınıfı tarafından kullanılmak üzere tasarlanmış [CRBMap](../../atl/reference/crbmap-class.md) ve [CRBMultiMap](../../atl/reference/crbmultimap-class.md). Bu türetilmiş sınıfları olun yöntemleri toplu tarafından sağlanan `CRBTree`.  
  
 Çeşitli koleksiyon sınıfları, özellikleri ve performans özelliklerini daha eksiksiz bir tartışma için bkz [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="cpair_class"></a>  CRBTree::CPair sınıfı  
 Anahtar ve değer öğeleri içeren bir sınıf.  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf yöntemler tarafından kullanılan [CRBTree::GetAt](#getat), [CRBTree::GetNext](#getnext), ve [CRBTree::GetPrev](#getprev) ağaç yapısında depolanmış anahtar ve değer öğeleri erişmek için.  
  
 Üyeleri aşağıdaki gibidir:  
  
|||  
|-|-|  
|`m_key`|Anahtar öğesi depolama veri üyesi.|  
|`m_value`|Değer öğesini depolama veri üyesi.|  
  
##  <a name="dtor"></a>  CRBTree:: ~ CRBTree  
 Yok Edicisi.  
  
```
~CRBTree() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır. Çağrıları [CRBTree::RemoveAll](#removeall) tüm öğeleri silmek için.  
  
##  <a name="findfirstkeyafter"></a>  CRBTree::FindFirstKeyAfter  
 Sonraki kullanılabilir anahtar kullanan öğenin konumunu bulmak için bu yöntemi çağırın.  
  
```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Bir anahtar değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Konum, bir sonraki kullanılabilir anahtarı kullanan öğenin değerini döndürür. Daha fazla öğe varsa, null değeri döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem konum değerleri önceden hesaplamak zorunda kalmadan ağacı gezme kolay hale getirir.  
  
##  <a name="getat"></a>  CRBTree::GetAt  
 Ağacında verilen konumda öğesini almak için bu yöntemi çağırın.  
  
```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Konum değeri.  
  
 `key`  
 Anahtarı aldıktan değişkeni.  
  
 *value*  
 Değerini alan değişken.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk iki forms bir işaretçi döndürmek bir [CPair](#cpair_class). Üçüncü formun bir anahtarı ve belirtilen konum için bir değer alır.  
  
### <a name="remarks"></a>Açıklamalar  
 Konum değerini daha önce bir yöntem çağrısı gibi belirlenebilir [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::GetTailPosition](#gettailposition).  
  
 Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır `pos` NULL değerine eşittir.  
  
##  <a name="getcount"></a>  CRBTree::GetCount  
 Öğe sayısını ağacında almak için bu yöntemi çağırın.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ağaçta depolanan (her anahtar/değer çifti bir öğedir) öğe sayısını döndürür.  
  
##  <a name="getheadposition"></a>  CRBTree::GetHeadPosition  
 Ağaç başındaki öğesi için konum değerini almak için bu yöntemi çağırın.  
  
```
POSITION GetHeadPosition() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ağaç başındaki öğesinin konum değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından döndürülen değer `GetHeadPosition` yöntemleriyle gibi kullanılabilir [CRBTree::GetKeyAt](#getkeyat) veya [CRBTree::GetNext](#getnext) ağacı gezme ve değerleri almak için.  
  
##  <a name="getkeyat"></a>  CRBTree::GetKeyAt  
 Ağacında belirli bir konumdan anahtarını almak için bu yöntemi çağırın.  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Konum değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Konumunda depolanan anahtar döndürür `pos` ağacında.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `pos` bir geçerli konumu değer sonuçları tahmin edilemez. Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır `pos` NULL değerine eşittir.  
  
##  <a name="getnext"></a>  CRBTree::GetNext  
 Depolanmış bir öğe için bir işaretçi elde etmek için bu yöntemi çağırın `CRBTree` nesne ve sonraki öğeye konumu ilerleyin.  
  
```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konumu sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonraki işaretçi döndüren [CPair](#cpair_class) ağacında değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 `pos` Konumu sayaç, her çağrısından sonra güncelleştirilir. Alınan öğe ağacında, son ise `pos` NULL olarak ayarlandı.  
  
##  <a name="getnextassoc"></a>  CRBTree::GetNextAssoc  
 Anahtar ve değer eşlemesinde depolanan bir öğenin almak için bu yöntemi çağırın ve sonraki öğeye konumu ilerleyin.  
  
```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konumu sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
 `key`  
 Şablon parametresi ağacının anahtar türü belirtme.  
  
 *value*  
 Şablon parametresi ağacının değerin türünü belirtme.  
  
### <a name="remarks"></a>Açıklamalar  
 `pos` Konumu sayaç, her çağrısından sonra güncelleştirilir. Alınan öğe ağacında, son ise `pos` NULL olarak ayarlandı.  
  
##  <a name="getnextkey"></a>  CRBTree::GetNextKey  
 Ağaçta depolanan bir öğenin anahtarı almak için bu yöntemi çağırın ve sonraki öğeye konumu ilerleyin.  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konumu sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ağaçta sonraki anahtarı için bir başvuru döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli konumu sayaç güncelleştirmeleri `pos`. Ağaçta daha fazla girdi yoksa konumu sayacı NULL olarak ayarlanır.  
  
##  <a name="getnextvalue"></a>  CRBTree::GetNextValue  
 Ağaçta depolanan bir öğe değerini almak için bu yöntemi çağırın ve sonraki öğeye konumu ilerleyin.  
  
```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konumu sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ağaçta sonraki değeri bir başvuru döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli konumu sayaç güncelleştirmeleri `pos`. Ağaçta daha fazla girdi yoksa konumu sayacı NULL olarak ayarlanır.  
  
##  <a name="getprev"></a>  CRBTree::GetPrev  
 Depolanmış bir öğe için bir işaretçi elde etmek için bu yöntemi çağırın `CRBTree` nesnesi ve ardından önceki öğesine konumu güncelleştirin.  
  
```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konumu sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşaretçi önceki döndüren [CPair](#cpair_class) ağacında depolanan değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli konumu sayaç güncelleştirmeleri `pos`. Ağaçta daha fazla girdi yoksa konumu sayacı NULL olarak ayarlanır.  
  
##  <a name="gettailposition"></a>  CRBTree::GetTailPosition  
 Ağaç kuyruğu öğede için konum değerini almak için bu yöntemi çağırın.  
  
```
POSITION GetTailPosition() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ağaç kuyruğu öğede konum değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından döndürülen değer `GetTailPosition` yöntemleriyle gibi kullanılabilir [CRBTree::GetKeyAt](#getkeyat) veya [CRBTree::GetPrev](#getprev) ağacı gezme ve değerleri almak için.  
  
##  <a name="getvalueat"></a>  CRBTree::GetValueAt  
 Belirli bir konumda depolanan değerini almak için bu yöntemi çağırın `CRBTree` nesnesi.  
  
```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konumu sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen konumunda depolanan değeri bir başvuru döndürür `CRBTree` nesnesi.  
  
##  <a name="isempty"></a>  CRBTree::IsEmpty  
 Bir boş ağaç nesne için test etmek için bu yöntemi çağırın.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** ağaç boşsa, **false** Aksi takdirde.  
  
##  <a name="kinargtype"></a>  CRBTree::KINARGTYPE  
 Bir giriş bağımsız değişkeni bir anahtar geçirildiğinde kullanılan türü.  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="koutargtype"></a>  CRBTree::KOUTARGTYPE  
 Bir anahtar çıkış bağımsız değişken olarak döndürüldüğünde kullanılan türü.  
  
```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```  
  
##  <a name="removeall"></a>  CRBTree::RemoveAll  
 Tüm öğeleri kaldırmak için bu yöntemi çağırın `CRBTree` nesnesi.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Temizler `CRBTree` öğeleri depolamak için kullanılan bellek boşaltma nesnesi.  
  
##  <a name="removeat"></a>  CRBTree::RemoveAt  
 Belirtilen konumda öğesini kaldırmak için bu yöntemi çağırın **CRBTree** nesnesi.  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konumu sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen konumda saklanan anahtar/değer çifti kaldırır. Öğe depolamak için kullanılan bellek serbest bırakılır. KONUM tarafından başvurulan `pos` geçersiz hale gelir ve diğer öğeleri KONUMUNU ağacında yapmaları gerekmez, geçerli kalırken aynı sırada korur.  
  
##  <a name="setvalueat"></a>  CRBTree::SetValueAt  
 Belirli bir konumda depolanan değeri değiştirmek için bu yöntemi çağırın `CRBTree` nesnesi.  
  
```
void SetValueAt(POSITION pos, VINARGTYPE value);
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konumu sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).  
  
 *value*  
 Eklenecek değer `CRBTree` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Verilen konumunda depolanan değer öğesini değiştirir `CRBTree` nesnesi.  
  
##  <a name="vinargtype"></a>  CRBTree::VINARGTYPE  
 Bir giriş bağımsız değişkeni bir değer geçirildiğinde kullanılan türü.  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="voutargtype"></a>  CRBTree::VOUTARGTYPE  
 Çıkış bağımsız değişken olarak bir değer geçirildiğinde kullanılan türü.  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
