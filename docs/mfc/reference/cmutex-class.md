---
title: "CMutex sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
dev_langs:
- C++
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d87d613356589ee192ef141a3e222fdc4d8f03f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmutex-class"></a>CMutex sınıfı
"Mutex" temsil eder — bir iş parçacığı birbirini dışlayan bir kaynağa erişim izni veren bir eşitleme nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMutex : public CSyncObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMutex::CMutex](#cmutex)|Oluşturan bir `CMutex` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman uyumu sağlayıcılar, veri veya başka bir denetimli kaynak değiştirmek için aynı anda yalnızca bir iş parçacığı izin olduğunda yararlıdır. Örneğin, düğümleri bağlantılı bir listesine ekleyerek bir iş parçacığı tarafından aynı anda yalnızca izin verilecek bir işlemdir. Kullanarak bir `CMutex` aynı anda tek bir iş parçacığı listesine erişebilir yalnızca bağlantılı liste denetlemek için nesne.  
  
 Kullanılacak bir `CMutex` nesne, oluşturmak `CMutex` nesne gerektiğinde. İstediğiniz beklemesi mutex adını belirtin ve uygulamanızı başlangıçta ait. Oluşturucusu döndürdüğünde mutex daha sonra erişebilirsiniz. Çağrı [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) işiniz bittiğinde kontrollü bir kaynağa erişme.  
  
 Kullanmak için alternatif bir yöntem `CMutex` nesnedir türünde bir değişken eklemek için `CMutex` denetimine istediğiniz sınıfı veri üyesi olarak. Denetlenen Nesne oluşturma sırasında oluşturucusunun çağrı `CMutex` veri üyesi mutex başlangıçta sahibi, (Bu işlem sınırlarında kullanılacaksa) mutex adını ve güvenlik öznitelikleri istenen belirtme.  
  
 Denetlenen kaynaklara erişmek için `CMutex` nesneleri bu şekilde ilk oluşturun ya da türünde bir değişken [CSingleLock](../../mfc/reference/csinglelock-class.md) veya türü [CMultiLock](../../mfc/reference/cmultilock-class.md) , kaynağın erişim üye fonksiyonu içinde. Kilit nesnenin çağrısı `Lock` üye işlevi (örneğin, [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). Bu noktada, iş parçacığı ya da kaynağa erişim, yayımlanması ve erişim kazanmak veya zaman aşımı, kaynağa erişmek başarısız olan ve kaynak yayımlanacak bekleyin kaynak için bekleyin. Her iki durumda da, kaynak, bir iş parçacığı açısından güvenli şekilde erişilmedi. Kaynak serbest bırakmak için kilit nesnenin kullanın `Unlock` üye işlevi (örneğin, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), veya kilit kapsamı dışında kalan nesnesine izin verin.  
  
 Kullanma hakkında daha fazla bilgi için `CMutex` nesneleri başlıklı makaleye bakın [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxmt.h  
  
##  <a name="cmutex"></a>CMutex::CMutex  
 Adlandırılmış veya adlandırılmamış oluşturur `CMutex` nesnesi.  
  
```  
CMutex(
    BOOL bInitiallyOwn = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `bInitiallyOwn`  
 Belirtir iş parçacığı oluşturma `CMutex` nesne başlangıçta tarafından mutex denetimli kaynak erişimi vardır.  
  
 `lpszName`  
 Adını `CMutex` nesnesi. Aynı ada sahip başka bir mutex varsa `lpszName` nesne işlem sınırlarında kullanılacaksa sağlanmalıdır. Varsa **NULL**, mutex adlandırılmamış olacaktır. Ad mevcut bir mutex eşleşirse, Oluşturucusu yeni yapılar `CMutex` adının mutex başvuruda bulunan nesne. Adı ile eşleşen bir mutex değil varolan bir eşitleme nesnesi oluşturma başarısız olur.  
  
 `lpsaAttribute`  
 Mutex nesnesi için güvenlik öznitelikler. Bu yapı tam bir açıklaması için bkz: [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK'sındaki.  
  
### <a name="remarks"></a>Açıklamalar  
 Erişim veya serbest bir `CMutex` nesne, oluşturma bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesne ve çağrı kendi [kilit](../../mfc/reference/csinglelock-class.md#lock) ve [Unlock](../../mfc/reference/csinglelock-class.md#unlock) üye işlevleri. Varsa `CMutex` nesne kullanılan tek başına, çağrı kendi `Unlock` üye işlevi bırakın.  
  
> [!IMPORTANT]
>  Oluşturduktan sonra `CMutex` nesne, kullanın [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) mutex zaten mevcut olduğundan emin olmak için. Mutex beklenmedik bir şekilde yoksa, dolandırıcı işlemin ele geçirilmesi ve mutex kötü amaçlı olarak kullanmayı planlayan gösterebilir. Bu durumda, önerilen güvenliğe tanıtıcı kapatın ve gibi varsa bir hata nesnesi oluşturulurken devam etmek için bir yordamdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSyncObject sınıfı](../../mfc/reference/csyncobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



