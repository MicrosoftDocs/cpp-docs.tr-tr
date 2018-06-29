---
title: Koleksiyon sınıfı Yardımcıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71871eae42fc720481852be1e60c934f941858c6
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078162"
---
# <a name="collection-class-helpers"></a>Koleksiyon Sınıfı Yardımcıları
Koleksiyon sınıfları `CMap`, `CList`, ve `CArray` karşılaştırma, kopyalama ve öğelerini serileştirme gibi amaçlarla şablonlu genel yardımcı işlevleri kullanın. Temel sınıflarının, uygulamanızı bir parçası olarak `CMap`, `CList`, ve `CArray`, eşlemesi, liste veya dizi depolanan verilerin türünü uyarlanmış sürümleriyle gerektikçe bu işlevleri geçersiz kılmalıdır. Yardımcı işlevleri gibi geçersiz kılma hakkında bilgi için `SerializeElements`, makaleye bakın [koleksiyonları: tür kullanımı uyumlu koleksiyon yapma](../../mfc/how-to-make-a-type-safe-collection.md). Unutmayın `ConstructElements` ve `DestructElements` kullanım dışı bırakıldı.  
  
 Microsoft Foundation Class Kitaplığı afxtempl.h koleksiyon sınıfları özelleştirmenize yardımcı olması için aşağıdaki genel işlevler sağlar:  
  
### <a name="collection-class-helpers"></a>Koleksiyon Sınıfı Yardımcıları  
  
|||  
|-|-|  
|[CompareElements](#compareelements)|Öğeler aynı olup olmadığını gösterir.|  
|[CopyElements](#copyelements)|Başka bir bir dizi öğeleri kopyalar.|  
|[DumpElements](#dumpelements)|Akış odaklı tanılama çıktıları sağlar.|  
|[HashKey](#hashkey)|Karma anahtar hesaplar.|  
|[SerializeElements](#serializeelements)|Bir arşiv öğelerin alır veya depolar.|  
  
##  <a name="compareelements"></a>  CompareElements  
 Doğrudan göre adlı [CList::Find] (clist class.md #not_found.md #clist__find ve dolaylı olarak [cmap__lookup](cmap-class.md#lookup) ve [cmap__operator &#91; &#93; ](cmap-class.md#operator_at).  
  
```   
template<class TYPE, class ARG_TYPE>  
BOOL AFXAPI  
CompareElements(
    const TYPE* pElement1,  
    const ARG_TYPE* pElement2);  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Karşılaştırılacak ilk öğe türü.  
  
 *pElement1*  
 Karşılaştırılacak ilk öğe işaretçi.  
  
 *ARG_TYPE*  
 Karşılaştırılacak ikinci öğe türü.  
  
 *pElement2*  
 Karşılaştırılacak ikinci öğesi işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne gösterdiği, sıfır olmayan *pElement1* gösterdiği nesnesine eşit olan *pElement2*; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `CMap` Çağırır kullanım `CMap` şablon parametreleri *anahtar* ve `ARG_KEY`.  
  
 Varsayılan uygulama karşılaştırması sonucunu döndürür  *\*pElement1* ve  *\*pElement2*. Böylece, uygulamanız için uygun şekilde öğeleri karşılaştırır bu işlev geçersiz kılar.  
  
 C++ dili karşılaştırma işleci tanımlar ( `==`) basit türleri için ( **char**, **int**, **float**, vb.) için bir karşılaştırma işleci tanımlamaz, ancak sınıfları ve yapıları. Kullanmak istiyorsanız, `CompareElements` veya kullandığı koleksiyon sınıfları birini örneği oluşturmak için karşılaştırma işleci tanımlama veya aşırı `CompareElements` bir sürümüyle uygun değerleri döndürür.  
  
### <a name="requirements"></a>Gereksinimler  
   **Başlık:** afxtempl.h   
  
##  <a name="copyelements"></a>  CopyElements  
 Bu işlev doğrudan göre adlandırılır [CArray::Append](carray-class.md#append) ve [CArray::Copy](carray-class.md#copy).  
  
```   
template<class TYPE>  
void AFXAPI CopyElements(
    TYPE* pDest,  
    const TYPE* pSrc,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Kopyalanacak öğelerin türünü belirten bir şablon parametre.  
  
 *pDest*  
 Öğelerin kopyalanacağı hedef işaretçi.  
  
 *pSrc*  
 İşaretçi kaynağına kopyalanacak öğe.  
  
 *nCount*  
 Kopyalanacak öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Basit atama işleci varsayılan uygulama kullanır ( **=** ) kopyalama işlemi gerçekleştirmek için. Kopyalanan türü aşırı yüklenmiş bir işleç yoksa varsayılan uygulama Bitsel kopyasını gerçekleştirir sonra =.  
  
 Makaleyi bu ve diğer yardımcı işlevleri uygulama hakkında daha fazla bilgi için bkz [koleksiyonları: tür kullanımı uyumlu koleksiyon yapma](../how-to-make-a-type-safe-collection.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxtempl.h  
  
##  <a name="dumpelements"></a>  DumpElements  
 Akış odaklı tanılama çıktıları metin biçiminde için geçersiz kılındığında, koleksiyonunuzu öğeleri sağlar.  
  
```   
template<class TYPE>  
void  AFXAPI DumpElements(
    CDumpContext& dc,  
    const TYPE* pElements,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parametreler  
 *DC*  
 Öğeleri dökme için bağlam dökümü.  
  
 *TÜRÜ*  
 Öğelerin türünü belirten bir şablon parametre.  
  
 *pElements*  
 Öğeleri dökümünün için işaretçi.  
  
 *nCount*  
 Dökümünün öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `CArray::Dump`, `CList::Dump`, Ve `CMap::Dump` işlevleri çağırmak, bu, döküm derinliği 0'dan büyük olması durumunda.  
  
 Varsayılan uygulama hiçbir şey yapmaz. Koleksiyonunuz öğelerini türetilmiş varsa `CObject`, geçersiz kılma koleksiyonun öğelerini aracılığıyla genellikle yinelemek çağırma `Dump` Aç her öğe için.  
  

### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxtempl.h  
  
##  <a name="hashkey"></a>  HashKey  
 Belirtilen anahtar için bir karma değer hesaplar.  
  
```  
template<class ARG_KEY>  
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key); 
```  
  
### <a name="parameters"></a>Parametreler  
 *ARG_KEY*  
 Şablon parametresi harita anahtarları erişmek için kullanılan veri türünü belirtme.  
  
 *Anahtarı*  
 Karma değeri hesaplanacak olan anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtarın karma değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev doğrudan göre adlandırılır [CMap::RemoveKey](cmap-class.md#removekey) ve dolaylı olarak [CMap::Lookup](cmap-class.md#lookup) ve [CMap::Operator &#91; &#93; ](cmap-class.md#operator_at).
  
 Varsayılan uygulama değiştirerek bir karma değer oluşturan *anahtar* dört konumlar sağ tarafından. Bu işlev, böylece karma değerleri, uygulamanız için uygun döndürür geçersiz kılar.  
  
### <a name="example"></a>Örnek
 ```cpp  
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number 
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
 ```
 
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxtempl.h 
  
##  <a name="serializeelements"></a>  SerializeElements  
 [CArray](carray-class.md), [CList](clist-class.md), ve [CMap](cmap-class.md) öğeleri seri hale getirmek için bu işlevini çağırın.  
  
```   
template<class TYPE>  
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Öğelerin türünü belirten bir şablon parametre.  
  
 *ar*  
 Gelen veya giden arşivlemek için bir arşiv nesne.  
  
 *pElements*  
 Arşivlenen öğeleri işaretçi.  
  
 *nCount*  
 Arşivlenen öğelerin sayısı  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama bit mu okuma veya yazma.  
  
 Makaleyi bu ve diğer yardımcı işlevleri uygulama hakkında daha fazla bilgi için bkz [koleksiyonları: tür kullanımı uyumlu koleksiyon yapma](../how-to-make-a-type-safe-collection.md).  
  
### <a name="example"></a>Örnek  
 Makaleyi örnekte bkz [koleksiyonları: tür kullanımı uyumlu koleksiyon yapma](../how-to-make-a-type-safe-collection.md).  
 
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxtempl.h 
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [CMap sınıfı](cmap-class.md)   
 [CList sınıfı](clist-class.md)   
 [CArray Sınıfı](carray-class.md)