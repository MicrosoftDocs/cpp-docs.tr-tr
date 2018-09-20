---
title: CSemaphore sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 19d43d108888d1d89b4fa6173ab3ebd0e8e55bbc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400256"
---
# <a name="csemaphore-class"></a>CSemaphore sınıfı

Sınıfın bir nesnesi `CSemaphore` "semafor" temsil eder; bir tutar erişmek için bir veya daha fazla işlem içinde belirtilen bir kaynak şu anda erişen iş parçacığı sayısını sınırlı sayıda iş parçacığının veren bir eşitleme nesnesi.

## <a name="syntax"></a>Sözdizimi

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSemaphore::CSemaphore](#csemaphore)|Oluşturur bir `CSemaphore` nesne.|

## <a name="remarks"></a>Açıklamalar

Semafor, yalnızca sınırlı sayıda kullanıcıları destekleyebilir paylaşılan bir kaynağa erişimi denetlemek yararlıdır. Geçerli sayısı `CSemaphore` nesnedir, izin verilen ek kullanıcıların sayısı. Sayısı sıfır ulaştığında, tüm çalışır tarafından denetlenen kaynağı `CSemaphore` nesne sistem kuyruğa eklenir ve bunlar kadar bekleyin ya da zaman aşımı veya 0'ın üzerinde sayısı yükseldiğinde. Denetimli kaynak tek seferde erişebilen kullanıcı sayısı oluşumu sırasında belirtilen `CSemaphore` nesne.

Kullanılacak bir `CSemaphore` nesne, oluşturmak `CSemaphore` gerektiğinde nesne. Üzerinde beklenilen istediğiniz semafor adını belirtin ve uygulamanızı başlangıçta ait. Oluşturucu döndürdüğünde semafor erişebilirsiniz. Çağrı [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) işiniz bittiğinde kontrollü bir kaynağa erişme.

Alternatif bir yöntem kullanarak `CSemaphore` türünde bir değişken eklemek için nesneleri, `CSemaphore` denetimine istediğiniz sınıfı için bir veri üyesi olarak. Denetlenen Nesne oluşturma sırasında oluşturucusuna çağrı `CSemaphore` ilk belirtme veri üyesi erişim sayısı, en fazla erişim sayısı, (Bu işlem sınırları ötesinde kullanılacaksa) semafor adını ve istenen güvenlik öznitelikleri.

Denetlenen kaynaklarına erişmek için `CSemaphore` nesnelere bu şekilde, ilk iki türünde bir değişken oluşturun [CSingleLock](../../mfc/reference/csinglelock-class.md) veya türü [CMultiLock](../../mfc/reference/cmultilock-class.md) kaynağınızın erişim üye işlev. Ardından kilit nesnenin çağrı `Lock` üye işlevi (örneğin, [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). Bu noktada, iş parçacığı ya da kaynağa erişim, kaynak serbest bırakılması ve erişim veya zaman aşımı, kaynağa erişmek başarısız olan ve kaynak yayımlanacak bekleyin için bekleyin. Her iki durumda da, kaynak, bir iş parçacığı açısından güvenli şekilde erişilmedi. Kaynağı serbest bırakmak için kilit nesnenin kullanın `Unlock` üye işlevi (örneğin, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), veya kilit nesne kapsam dışına düşen izin verin.

Alternatif olarak, oluşturabileceğiniz bir `CSemaphore` tek başına nesne ve denetimli bir kaynağa erişmeyi denemeden önce açıkça erişim. Bu, kaynak kodunuzu okuyan kişi daha anlaşılır sırasında daha fazla hataya yöntemidir.

Nasıl kullanılacağı hakkında daha fazla bilgi için `CSemaphore` nesneleri başlıklı makaleye bakın [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt.h

##  <a name="csemaphore"></a>  CSemaphore::CSemaphore

Adlandırışmış veya adlandırılmamış bir yapıları `CSemaphore` nesne.

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>Parametreler

*lInitialCount*<br/>
Semafor için ilk kullanım sayısı. En az 0 olmalıdır ve daha az veya buna eşit *lMaxCount*.

*lMaxCount*<br/>
Semafor için en fazla kullanım sayısı. 0'dan büyük olmalıdır.

*pstrName*<br/>
Semafor adı. Semafor işlem sınırları ötesinde erişecek olursa sağlanmalıdır. Varsa `NULL`, nesne adlandırılmamış olacaktır. Oluşturucu ad var olan bir semaforu eşleşiyorsa, yeni bir yapılar `CSemaphore` adının semafor başvuran nesne. Semafor olmayan mevcut bir eşitleme nesnesi adıyla, yapı başarısız olur.

*lpsaAttributes*<br/>
Semafor nesne için güvenlik öznitelikleri. Bu yapı tam bir açıklaması için bkz. [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK.

### <a name="remarks"></a>Açıklamalar

Erişim veya yayın için bir `CSemaphore` nesne, oluşturun bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesne ve çağrı kendi [kilit](../../mfc/reference/csinglelock-class.md#lock) ve [kilidini](../../mfc/reference/csinglelock-class.md#unlock) üye işlevleri.

> [!IMPORTANT]
>  Oluşturduktan sonra `CSemaphore` nesnesi [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) mutex zaten yoktu emin olmak için. Mutex beklenmedik bir şekilde mevcut olması, dolandırıcı işlemin ele geçirilmesi ve mutex kötü amaçlı olarak kullanmayı planlayan gösterebilir. Bu durumda, tanıtıcı kapatın ve var olan bir hata varmış gibi nesnesi oluşturulurken devam etmek için önerilen güvenliğe yordam aynıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[CSyncObject Sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



