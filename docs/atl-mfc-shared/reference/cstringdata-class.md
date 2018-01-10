---
title: "CStringData sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringData
- ATLSIMPSTR/ATL::CStringData
- ATLSIMPSTR/ATL::AddRef
- ATLSIMPSTR/ATL::data
- ATLSIMPSTR/ATL::IsLocked
- ATLSIMPSTR/ATL::IsShared
- ATLSIMPSTR/ATL::Lock
- ATLSIMPSTR/ATL::Release
- ATLSIMPSTR/ATL::Unlock
- ATLSIMPSTR/ATL::nAllocLength
- ATLSIMPSTR/ATL::nDataLength
- ATLSIMPSTR/ATL::nRefs
- ATLSIMPSTR/ATL::pStringMgr
dev_langs: C++
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7523ca52c0ded8ec9b3cf02dd6798beca8be5cf8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cstringdata-class"></a>CStringData sınıfı
Bu sınıf, bir dize nesnesi verileri temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
struct CStringData
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AddRef](#addref)|Dize veri nesnesinin başvurusu sayısını artırır.|  
|[veri](#data)|Bir dize nesnesi karakter verileri alır.|  
|[IsLocked](#islocked)|İlişkili dize nesnesi arabellek kilitliyse belirler.|  
|[IsShared](#isshared)|İlişkili dize nesnesi arabellek şu anda paylaşılan belirler.|  
|[Kilitleme](#lock)|İlişkili dize nesnesi arabellek kilitler.|  
|[Sürüm](#release)|Belirtilen dize nesnesi serbest bırakır.|  
|[Kilidini aç](#unlock)|İlişkili dize nesnesi arabellek kilidini açar.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[nAllocLength](#nalloclength)|Ayrılmış veri uzunluğu `XCHAR`s (içermeyen sonlandırma null)|  
|[nDataLength](#ndatalength)|Şu anda kullanılan veri uzunluğu `XCHAR`s (içermeyen sonlandırma null)|  
|[nRefs](#nrefs)|Nesnenin geçerli başvuru sayısı.|  
|[pStringMgr](#pstringmgr)|Bu dize nesnesinin dize Yöneticisi için bir işaretçi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf yalnızca özel bir dize yöneticileri uygulama geliştiriciler tarafından kullanılması gerekir. Özel bir dize yöneticileri hakkında daha fazla bilgi için bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)  
  
 Bu sınıf çeşitli bilgi ve daha yüksek bir dize nesnesi ile ilişkili veri türlerini yalıtır [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), veya [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) nesneleri. Her daha yüksek bir dize nesnesi, ilişkili bir işaretçi içeriyor `CStringData` nesnesi, aynı dize veri nesnesine işaret edecek şekilde birden çok dize nesnelerini izin verme. Bu ilişki başvuru sayısı tarafından temsil edilen ( `nRefs`), `CStringData` nesnesi.  
  
> [!NOTE]
>  Bazı durumlarda, bir dize türü (gibi **CFixedString**) bir dize veri nesnesi ile birden çok daha yüksek dize nesnesi paylaşmaz. Bunun hakkında daha fazla bilgi için bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 Bu veriler, şunlardan oluşur:  
  
-   Bellek Yöneticisi'ni (tür [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) dizesi.  
  
-   Geçerli uzunluğu ( [nDataLength](#ndatalength)) dizesi.  
  
-   Ayrılmış uzunluğu ( [nAllocLength](#nalloclength)) dizesi. Performans nedeniyle, bu geçerli bir dize uzunluğu farklı olabilir  
  
-   Geçerli başvuru sayısı ( [nRefs](#nrefs)), `CStringData` nesnesi. Bu değer kaç string nesneleri aynı paylaşan belirlerken kullanılır `CStringData` nesnesi.  
  
-   Gerçek karakter arabellek ( [veri](#data)) dizesi.  
  
    > [!NOTE]
    >  Dize nesnesi gerçek karakter arabelleğin dize Yöneticisi tarafından ayrılmış ve eklenir `CStringData` nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpstr.h  
  
##  <a name="addref"></a>CStringData::AddRef  
 Dize nesnesi başvurusu sayısını artırır.  
  
```
void AddRef() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dize nesnesi başvurusu sayısını artırır.  
  
> [!NOTE]
>  Negatif bir sayı dizesi arabelleği kilitli olup olmadığını gösterir. bu yana bir dize bir eksi başvuru sayısı üzerinde bu yöntemi çağırmayın.  
  
##  <a name="data"></a>CStringData::data  
 Bir işaretçi bir dize nesnesi karakteri arabelleğe döndürür.  
  
```
void* data() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dize nesnesi karakter arabelleği için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 İlişkili dize nesnesi geçerli karakter arabelleğin döndürmek için bu işlevini çağırın.  
  
> [!NOTE]
>  Bu arabellek tarafından ayrılmamış `CStringData` nesnesi, ancak gerektiğinde dize Yöneticisi tarafından. Ayrılmış, arabellek dize veri nesnesine eklenir.  
  
##  <a name="islocked"></a>CStringData::IsLocked  
 Karakter arabellek kilitliyse belirler.  
  
```
bool IsLocked() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** arabellek kilitli; tersi durumda ise **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bir dize nesnesi karakter arabelleğin şu anda kilitli belirlemek için çağrılır.  
  
##  <a name="isshared"></a>CStringData::IsShared  
 Karakter arabellek paylaşılıp paylaşılmadığını belirler.  
  
```
bool IsShared() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** arabellek, paylaşılan aksi **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Dize veri nesnesinin karakter arabellek şu anda birden çok dize nesne arasında paylaşılıp paylaşılmadığını belirlemek için bu işlevini çağırın.  
  
##  <a name="lock"></a>CStringData::Lock  
 İlişkili dize nesnesi karakter arabelleğin kilitler.  
  
```
void Lock() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dize veri nesnesinin karakter arabelleği kilitlemek için bu işlevini çağırın. Karakter arabellek doğrudan erişim geliştirici tarafından istendiğinde kilitleme ve kilidini açma kullanılır. Kilitleme iyi bir örneği tarafından gösterilen [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) ve [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) yöntemlerini `CSimpleStringT`.  
  
> [!NOTE]
>  Arabellek yüksek dize nesneler arasında paylaşılmayan varsa bir karakter arabellek yalnızca kilitlenebilir.  
  
##  <a name="nalloclength"></a>CStringData::nAllocLength  
 Ayrılmış karakter arabellek uzunluğu.  
  
```
int nAllocLength;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış veri arabellek uzunluğu depolar `XCHAR`s (içermeyen sonlandırma null).  
  
##  <a name="ndatalength"></a>CStringData::nDataLength  
 Dize nesnesi geçerli uzunluğu.  
  
```
int nDataLength;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şu anda kullanılan veri uzunluğu depolar `XCHAR`s (içermeyen sonlandırma null).  
  
##  <a name="nrefs"></a>CStringData::nRefs  
 Dize veri nesnesi başvuru sayısı.  
  
```
long nRefs;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dize veri nesnesi başvuru sayısı depolar. Bu sayı dize veri nesnesiyle ilişkili yüksek dize nesne sayısını gösterir. Dize veri nesnesi şu anda kilitli negatif bir değer gösterir.  
  
##  <a name="pstringmgr"></a>CStringData::pStringMgr  
 Bellek Yöneticisi'nin ilişkili dize nesnesi.  
  
```
IAtlStringMgr* pStringMgr;
```  
  
### <a name="remarks"></a>Açıklamalar  
 İlişkili dize nesnesi için bellek yöneticisi depolar. Bellek yöneticilerini ve dizeleri hakkında daha fazla bilgi için bkz: [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="release"></a>CStringData::Release  
 Başvuru sayım dize veri nesnesi azaltır.  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başvuru sayısı düşürmek için bu işlevi çağırmak boşaltma `CStringData` başvuru sayısı sıfır değerse yapılandırın. Bu, genellikle bir dize nesnesi silinir ve bu nedenle artık dize veri nesnesi başvurmalıdır gerçekleştirilir.  
  
 Örneğin, aşağıdaki kodu çağırırdı `CStringData::Release` dize veri nesnesi ile ilişkili `str1`:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]  
  
##  <a name="unlock"></a>CStringData::Unlock  
 İlişkili dize nesnesi karakter arabelleğin kilidini açar.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dize veri nesnesinin karakter arabellek kilidini açmak için bu işlevini çağırın. Arabellek kilidi olduğunda paylaşılabilir ve başvuru sayılamaz.  
  
> [!NOTE]
>  Her çağrı `Lock` karşılık gelen çağrısı ile eşleşmesi gereken `Unlock`.  
  
 Geliştirici dize verilerini değil paylaşılması emin olmalısınız kilitleme ve kilidini açma kullanılır. Kilitleme iyi bir örneği tarafından gösterilen [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) ve [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) yöntemlerini `CSimpleStringT`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [ATL/MFC sınıfları paylaşılan](../../atl-mfc-shared/atl-mfc-shared-classes.md)


