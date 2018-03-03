---
title: "CSemaphore sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
dev_langs:
- C++
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 378007ee4ebbb457fb8922d44d063b3bdf05729d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csemaphore-class"></a>CSemaphore sınıfı
Sınıfın bir nesnesi `CSemaphore` "semafor" temsil eder — bir tutar erişmek için bir veya daha fazla işlemde şu anda belirtilen kaynağa erişme iş parçacıklarının sayısını sınırlı sayıda iş parçacığına veren bir eşitleme nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSemaphore : public CSyncObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSemaphore::CSemaphore](#csemaphore)|Oluşturan bir `CSemaphore` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Semafor yalnızca sınırlı sayıda kullanıcının destekleyebilir paylaşılan bir kaynağa erişimi denetleme faydalıdır. Geçerli sayısını `CSemaphore` nesne izin verilen ek kullanıcı sayısıdır. Sayısı sıfır ulaşırsa, tüm çalışır denetlediği kaynağı kullanmak **CSemaphore** nesnesi bir sistem kuyruğa eklenir ve bunlar kadar bekleyin ya da zaman aşımı veya sayısı 0'ın üzerinde miktarı artar. Denetimli kaynak aynı anda erişebilecek kullanıcı sayısının oluşturma işlemi sırasında belirtilen `CSemaphore` nesnesi.  
  
 Kullanılacak bir **CSemaphore** nesne, oluşturmak `CSemaphore` nesne gerektiğinde. İstediğiniz beklemesi semafor adını belirtin ve uygulamanızı başlangıçta ait. Oluşturucusu döndürdüğünde semafor daha sonra erişebilirsiniz. Çağrı [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) işiniz bittiğinde kontrollü bir kaynağa erişme.  
  
 Kullanmak için alternatif bir yöntem `CSemaphore` nesnedir türünde bir değişken eklemek için `CSemaphore` denetimine istediğiniz sınıfı veri üyesi olarak. Denetlenen Nesne oluşturma sırasında oluşturucusunun çağrı `CSemaphore` ilk belirtme veri üyesi erişim sayısı, en fazla erişim sayısı, (Bu işlem sınırlarında kullanılacaksa) semafor adını ve güvenlik öznitelikleri istenen.  
  
 Denetlenen kaynaklara erişmek için `CSemaphore` nesneleri bu şekilde ilk oluşturun ya da türünde bir değişken [CSingleLock](../../mfc/reference/csinglelock-class.md) veya türü [CMultiLock](../../mfc/reference/cmultilock-class.md) , kaynağın erişim üye fonksiyonu içinde. Kilit nesnenin çağrısı `Lock` üye işlevi (örneğin, [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). Bu noktada, iş parçacığı ya da kaynağa erişim, yayımlanması ve erişim kazanmak veya zaman aşımı, kaynağa erişmek başarısız olan ve kaynak yayımlanacak bekleyin kaynak için bekleyin. Her iki durumda da, kaynak, bir iş parçacığı açısından güvenli şekilde erişilmedi. Kaynak serbest bırakmak için kilit nesnenin kullanın `Unlock` üye işlevi (örneğin, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), veya kilit kapsamı dışında kalan nesnesine izin verin.  
  
 Alternatif olarak, oluşturabileceğiniz bir **CSemaphore** tek başına nesne ve kontrollü bir kaynağa erişmeyi denemeden önce açıkça erişim. Bu, daha anlaşılır birisi, kaynak kodu okuma sırasında daha hataya yöntemidir.  
  
 Nasıl kullanılacağı hakkında daha fazla bilgi için **CSemaphore** nesneleri başlıklı makaleye bakın [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CSemaphore`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmt.h  
  
##  <a name="csemaphore"></a>CSemaphore::CSemaphore  
 Adlandırılmış veya adlandırılmamış oluşturur `CSemaphore` nesnesi.  
  
```  
CSemaphore(
    LONG lInitialCount = 1,  
    LONG lMaxCount = 1,  
    LPCTSTR pstrName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *lInitialCount*  
 Semafor için ilk kullanım sayısı. Büyük veya 0 olmalıdır ve küçük veya eşit `lMaxCount`.  
  
 `lMaxCount`  
 Semafor için en fazla kullanım sayısı. 0'dan büyük olmalıdır.  
  
 `pstrName`  
 Semafor adı. Semafor işlem sınırlarında erişecek olursa sağlanmalıdır. Varsa `NULL`, nesne adlandırılmamış olacaktır. Ad mevcut bir semafor eşleşirse, Oluşturucusu yeni yapılar `CSemaphore` adının semafor başvuruda bulunan nesne. Semafor değil varolan bir eşitleme nesnesi adıyla eşleşen oluşturma başarısız olur.  
  
 *lpsaAttributes*  
 Semafor nesne için güvenlik öznitelikler. Bu yapı tam bir açıklaması için bkz: [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK'sındaki.  
  
### <a name="remarks"></a>Açıklamalar  
 Erişim veya serbest bir `CSemaphore` nesne, oluşturma bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesne ve çağrı kendi [kilit](../../mfc/reference/csinglelock-class.md#lock) ve [Unlock](../../mfc/reference/csinglelock-class.md#unlock) üye işlevleri.  
  
> [!IMPORTANT]
>  Oluşturduktan sonra `CSemaphore` nesne, kullanın [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) mutex zaten mevcut olduğundan emin olmak için. Mutex beklenmedik bir şekilde yoksa, dolandırıcı işlemin ele geçirilmesi ve mutex kötü amaçlı olarak kullanmayı planlayan gösterebilir. Bu durumda, önerilen güvenliğe tanıtıcı kapatın ve gibi varsa bir hata nesnesi oluşturulurken devam etmek için bir yordamdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSyncObject sınıfı](../../mfc/reference/csyncobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



