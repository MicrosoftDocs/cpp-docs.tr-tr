---
title: "CSingleLock sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CSingleLock [MFC], CSingleLock
- CSingleLock [MFC], IsLocked
- CSingleLock [MFC], Lock
- CSingleLock [MFC], Unlock
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0dd07d79c97a9fb3368d20ee68df2332ba7ce5cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="csinglelock-class"></a>CSingleLock sınıfı
Birden çok iş parçacıklı programda bir kaynağa erişimi denetlemek kullanılan erişim denetim mekanizmasını temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSingleLock  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSingleLock::CSingleLock](#csinglelock)|Oluşturan bir `CSingleLock` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSingleLock::IsLocked](#islocked)|Nesne kilitli olduğunu belirler.|  
|[CSingleLock::Lock](#lock)|Eşitleme nesnesi üzerinde bekler.|  
|[CSingleLock::Unlock](#unlock)|Eşitleme nesnesi serbest bırakır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CSingleLock`bir taban sınıfı yok.  
  
 Eşitleme sınıfları kullanmak için [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), ve [CEvent](../../mfc/reference/cevent-class.md), ya da oluşturmalısınız bir `CSingleLock` veya [CMultiLock](../../mfc/reference/cmultilock-class.md) nesne beklemesi ve eşitleme nesnesi serbest bırakın. Kullanım `CSingleLock` yalnızca gerektiğinde bir nesne üzerinde aynı anda beklenecek. Kullanmak **CMultiLock** belirli bir zamanda kullanabileceğinizi birden fazla nesne olduğunda.  
  
 Kullanılacak bir `CSingleLock` nesne, denetlenen kaynağın sınıfında kurucusu üye fonksiyonu içinde çağırın. ' I çağırın [IsLocked](#islocked) kaynak olup olmadığını belirlemek için üye işlevi. İse, üye işlevini geri kalanı ile devam edin. Kaynak kullanılamıyorsa, zaman yayımlanacak kaynak için belirtilen miktarı bekleyin ya da hata döndürür. Kaynak kullanımını tamamlandıktan sonra ya da çağrısı [Unlock](#unlock) , işlev `CSingleLock` nesnesidir izin ver veya yeniden kullanılmak üzere `CSingleLock` yok edilmesi için nesne.  
  
 `CSingleLock`türetilen bir nesne varlığını gerektiren nesneleri [CSyncObject](../../mfc/reference/csyncobject-class.md). Bu genellikle bir veri denetimli kaynağın sınıfı üyesidir. Nasıl kullanılacağı hakkında daha fazla bilgi için `CSingleLock` nesneleri başlıklı makaleye bakın [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CSingleLock`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmt.h  
  
##  <a name="csinglelock"></a>CSingleLock::CSingleLock  
 Oluşturan bir `CSingleLock` nesnesi.  
  
```  
explicit CSingleLock(
    CSyncObject* pObject,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pObject`  
 Erişilecek eşitleme nesnesi noktalarına. Olamaz **NULL**.  
  
 `bInitialLock`  
 Başlangıçta belirtilen nesnenin erişme girişimi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev genellikle denetimli kaynak içinde bir erişim üye işlevi çağrılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#19](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]  
  
##  <a name="islocked"></a>CSingleLock::IsLocked  
 Nesne ile ilişkili ise belirler `CSingleLock` nesnesidir nonsignaled (kullanılamaz).  
  
```  
BOOL IsLocked();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne kilitliyse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#20](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]  
  
##  <a name="lock"></a>CSingleLock::Lock  
 İçin sağlanan eşitleme nesnesi tarafından denetlenen kaynak erişim kazanmak için bu işlevi çağırmak `CSingleLock` Oluşturucusu.  
  
```  
BOOL Lock(DWORD dwTimeOut = INFINITE);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwTimeOut*  
 Eşitleme nesnenin kullanılabilir olması için beklenecek süreyi belirtir (işaret). Varsa **SONSUZ**, `Lock` nesne döndürmeden önce işaret kadar bekler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Eşitleme nesnesi işaret edildiyse `Lock` başarıyla döndürür ve iş parçacığı şimdi nesnenin sahibi. Eşitleme nesnesi nonsignaled ise (kullanılamaz), `Lock` eşitleme nesne belirtilen milisaniye sayısı kadar işaret hale bekleyecek *dwTimeOut* parametresi. Eşitleme nesnesi belirtilen sürede, işaret hale değil, `Lock` hatasını döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
##  <a name="unlock"></a>CSingleLock::Unlock  
 Sahibi eşitleme nesnesi serbest `CSingleLock`.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lCount`  
 Serbest bırakmak için sağlanan erişim sayısı. 0'dan büyük olmalıdır. Belirtilen süre nesnenin sayısı maksimum değerini aşmasına neden olur, count değiştirilmez ve işlevi döndürür **FALSE**.  
  
 `lPrevCount`  
 Eşitleme nesnesi önceki sayısı almak için bir değişken noktalarına. Varsa **NULL**, önceki sayısı alınmadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlev başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev tarafından çağrılır `CSingleLock`'s yıkıcı.  
  
 Semafor birden fazla erişim sayısı yayın ihtiyacınız varsa, ikinci biçiminde kullanmak `Unlock` ve serbest bırakmak için sağlanan erişim sayısı belirtin.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_Utilities#21](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CMultiLock sınıfı](../../mfc/reference/cmultilock-class.md)
