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
ms.openlocfilehash: 6607f70a18734310d184c5cdd05d1e87f1b82d35
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852362"
---
# <a name="collection-class-helpers"></a>Koleksiyon Sınıfı Yardımcıları
Koleksiyon sınıfları `CMap`, `CList`, ve `CArray` karşılaştırma, kopyalama ve öğeleri seri hale getirme gibi amaçlar için şablonlu genel yardımcı işlevleri kullanın. Temel sınıflar, uygulamanızın bir parçası olarak `CMap`, `CList`, ve `CArray`, gerektiğinde bu işlevlerin sürümleri eşlemesi, liste veya dizi depolanan verilerin türünü uyarlanmış geçersiz kılmanız gerekir. Gibi yardımcı işlevleri geçersiz kılma hakkında daha fazla bilgi için `SerializeElements`, makaleye göz atın [koleksiyonları: tür kullanımı uyumlu koleksiyon yapma](../../mfc/how-to-make-a-type-safe-collection.md). Unutmayın `ConstructElements` ve `DestructElements` kullanım dışı bırakıldı.  
  
 Microsoft Foundation Class Kitaplığı afxtempl.h koleksiyon sınıflarınızı özelleştirmenize yardımcı olması için aşağıdaki genel işlevler sağlar:  
  
### <a name="collection-class-helpers"></a>Koleksiyon Sınıfı Yardımcıları  
  
|||  
|-|-|  
|[CompareElements](#compareelements)|Öğeler aynı olup olmadığını gösterir.|  
|[CopyElements](#copyelements)|Diğer bir dizi öğeleri kopyalar.|  
|[DumpElements](#dumpelements)|Akış odaklı tanılama çıkışı sağlar.|  
|[HashKey](#hashkey)|Bir karma anahtar hesaplar.|  
|[SerializeElements](#serializeelements)|Depolar veya için veya bir arşiv öğeleri alır.|  
  
##  <a name="compareelements"></a>  CompareElements  
 Doğrudan göre adlı [CList::Find] (#not_found.md #clist__find clist class.md ve dolaylı olarak [cmap__lookup](cmap-class.md#lookup) ve [cmap__operator &#91; &#93; ](cmap-class.md#operator_at).  
  
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
 Karşılaştırılacak ilk öğesinin işaretçisi.  
  
 *ARG_TYPE*  
 Karşılaştırılacak ikinci öğe türü.  
  
 *pElement2*  
 Karşılaştırılacak ikinci öğe işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesneyi işaret ettiği olursa sıfır dışı *pElement1* işaret ettiği nesnenin eşit olup *pElement2*; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `CMap` Çağırır kullanım `CMap` şablon parametreleri *anahtarı* ve *ARG_KEY*.  
  
 Varsayılan uygulama Karşılaştırma işleminin sonucunu döndürür  *\*pElement1* ve  *\*pElement2*. Bu işlev, böylece uygulamanız için uygun bir şekilde öğeleri karşılaştırır geçersiz kılar.  
  
 C++ dili karşılaştırma işleci tanımlar ( `==`) basit türleri için (**char**, **int**, **float**, vb.) için bir karşılaştırma işleci tanımlamıyor ancak sınıflar ve yapılar. Kullanmak istiyorsanız `CompareElements` veya aşağıdakilerden birini kullanan koleksiyon sınıfları oluşturmak için gereken karşılaştırma işleci tanımlama ya da aşırı `CompareElements` bir sürümle uygun değerleri döndürür.  
  
### <a name="requirements"></a>Gereksinimler  
   **Başlık:** afxtempl.h   
  
##  <a name="copyelements"></a>  CopyElements  
 Bu işlev tarafından doğrudan çağrılır [CArray::Append](carray-class.md#append) ve [CArray::Copy](carray-class.md#copy).  
  
```   
template<class TYPE>  
void AFXAPI CopyElements(
    TYPE* pDest,  
    const TYPE* pSrc,  
    INT_PTR nCount);  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Kopyalanacak öğe türünü belirten bir şablon parametre.  
  
 *pDest*  
 Öğelerin kopyalanacağı hedefe yönelik işaretçi.  
  
 *pSrc*  
 Kopyalanacak öğe kaynağı işaretçisi.  
  
 *nCount*  
 Kopyalanacak öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama kullanan basit atama işleci ( **=** ) kopyalama işlemini gerçekleştirmek için. Kopyalanan türü aşırı yüklenmiş bir işleç yoksa varsayılan uygulama bit düzeyinde bir kopyalama gerçekleştirir. ardından, =.  
  
 Uygulama bu ve diğer yardımcı işlevleri hakkında daha fazla bilgi için bkz [koleksiyonları: tür kullanımı uyumlu koleksiyon yapma](../how-to-make-a-type-safe-collection.md).  
  
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxtempl.h  
  
##  <a name="dumpelements"></a>  DumpElements  
 Tanılama çıkışı metin biçiminde akış temelli koleksiyonunuzun geçersiz kılındığında öğeleri sağlar.  
  
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
 Dökümü öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `CArray::Dump`, `CList::Dump`, Ve `CMap::Dump` işlevlerini çağıran, bu, döküm derinliği 0'dan büyükse.  
  
 Varsayılan uygulama, hiçbir şey yapmaz. Koleksiyon öğelerini türetilmiştir, `CObject`, geçersiz kılma genellikle koleksiyonun öğeleri yineleme çağırma `Dump` sırayla her öğe için.  
  

### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxtempl.h  
  
##  <a name="hashkey"></a>  HashKey  
 Belirtilen anahtar için bir karma değer hesaplar.  
  
```  
template<class ARG_KEY>  
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key); 
```  
  
### <a name="parameters"></a>Parametreler  
 *ARG_KEY*  
 Harita anahtarlarını erişmek için kullanılan veri türü belirten bir şablon parametre.  
  
 *Anahtarı*  
 Karma değeri hesaplanacak olan anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtarın karma değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev tarafından doğrudan çağrılır [CMap::RemoveKey](cmap-class.md#removekey) ve dolaylı olarak [CMap::Lookup](cmap-class.md#lookup) ve [CMap::Operator &#91; &#93; ](cmap-class.md#operator_at).
  
 Varsayılan uygulama değiştirerek bir karma değer oluşturur. *anahtar* şu dört konumları tarafından. Bu işlev, böylece uygulamanız için uygun karma değerlerini döndürür geçersiz kılar.  
  
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
  **Üst bilgi** afxtempl.h 
  
##  <a name="serializeelements"></a>  SerializeElements  
 [CArray](carray-class.md), [CList](clist-class.md), ve [CMap](cmap-class.md) öğelerini serileştirmek için bu işlevi çağırın.  
  
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
 Arşivlenen öğeleri işaretçisi.  
  
 *nCount*  
 Arşivlenen öğe sayısı  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama bit düzeyinde mu okuma veya yazma.  
  
 Uygulama bu ve diğer yardımcı işlevleri hakkında daha fazla bilgi için bkz [koleksiyonları: tür kullanımı uyumlu koleksiyon yapma](../how-to-make-a-type-safe-collection.md).  
  
### <a name="example"></a>Örnek  
 Makaleyi örneğe bakın [koleksiyonları: tür kullanımı uyumlu koleksiyon yapma](../how-to-make-a-type-safe-collection.md).  
 
### <a name="requirements"></a>Gereksinimler  
  **Üst bilgi** afxtempl.h 
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)   
 [CMap sınıfı](cmap-class.md)   
 [CList sınıfı](clist-class.md)   
 [CArray Sınıfı](carray-class.md)