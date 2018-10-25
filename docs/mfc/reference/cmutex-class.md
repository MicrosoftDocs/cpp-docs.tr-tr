---
title: CMutex sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23270275103faac3af48a3627a5f5833140645e2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50066759"
---
# <a name="cmutex-class"></a>CMutex sınıfı

"Mutex" temsil eder; bir iş parçacığı bir kaynağa karşılıklı olarak dışlama erişimine izin veren bir eşitleme nesnesi.

## <a name="syntax"></a>Sözdizimi

```
class CMutex : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMutex::CMutex](#cmutex)|Oluşturur bir `CMutex` nesne.|

## <a name="remarks"></a>Açıklamalar

Veri veya denetlenen başka bir kaynak değiştirmek için aynı anda yalnızca tek bir iş parçacığı izin verildiğinde Mutex'leri yararlı olur. Örneğin, bağlı bir liste düğüm ekleme, yalnızca tek bir iş parçacığı tarafından aynı anda izin verilmesi, bir işlemdir. Kullanarak bir `CMutex` öbekleri bağlantılı listede aynı anda tek bir iş parçacığı listesine ulaşmak yalnızca denetlemek için nesne.

Kullanılacak bir `CMutex` nesne, oluşturmak `CMutex` gerektiğinde nesne. Üzerinde beklenilen istediğiniz mutex adını belirtin ve uygulamanızı başlangıçta ait. Oluşturucu döndürdüğünde mutex erişebilirsiniz. Çağrı [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) işiniz bittiğinde kontrollü bir kaynağa erişme.

Alternatif bir yöntem kullanarak `CMutex` türünde bir değişken eklemek için nesneleri, `CMutex` denetimine istediğiniz sınıfı için bir veri üyesi olarak. Denetlenen Nesne oluşturma sırasında oluşturucusuna çağrı `CMutex` mutex ilk başta aitse, mutex (işlem sınırları arasında kullanılacak olan ise), adını ve istenen güvenlik öznitelikleri belirterek veri üyesi.

Denetlenen kaynaklarına erişmek için `CMutex` nesnelere bu şekilde, ilk iki türünde bir değişken oluşturun [CSingleLock](../../mfc/reference/csinglelock-class.md) veya türü [CMultiLock](../../mfc/reference/cmultilock-class.md) kaynağınızın erişim üye işlev. Ardından kilit nesnenin çağrı `Lock` üye işlevi (örneğin, [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). Bu noktada, iş parçacığı ya da kaynağa erişim, kaynak serbest bırakılması ve erişim veya zaman aşımı, kaynağa erişmek başarısız olan ve kaynak yayımlanacak bekleyin için bekleyin. Her iki durumda da, kaynak, bir iş parçacığı açısından güvenli şekilde erişilmedi. Kaynağı serbest bırakmak için kilit nesnenin kullanın `Unlock` üye işlevi (örneğin, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), veya kilit nesne kapsam dışına düşen izin verin.

Kullanma hakkında daha fazla bilgi için `CMutex` nesneleri başlıklı makaleye bakın [çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CMutex`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt.h

##  <a name="cmutex"></a>  CMutex::CMutex

Adlandırışmış veya adlandırılmamış bir yapıları `CMutex` nesne.

```
CMutex(
    BOOL bInitiallyOwn = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>Parametreler

*bInitiallyOwn*<br/>
Belirtir iş parçacığı oluşturma `CMutex` nesnenin başlangıçta mutex tarafından denetlenen kaynağa erişimi vardır.

*lpszName*<br/>
Adını `CMutex` nesne. Aynı ada sahip başka bir mutex varsa *lpszName* işlem sınırları ötesinde nesneye kullanılacaksa sağlanmalıdır. Varsa **NULL**, mutex adlandırılmamış olacaktır. Oluşturucu ad var olan bir mutex eşleşiyorsa, yeni bir yapılar `CMutex` başvuran adının mutex nesnesi. Adla eşleşen bir mutex olmayan mevcut bir eşitleme nesnesi oluşturma başarısız olur.

*lpsaAttribute*<br/>
Mutex nesnesi için güvenlik öznitelikleri. Bu yapı tam bir açıklaması için bkz. [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) Windows SDK.

### <a name="remarks"></a>Açıklamalar

Erişim veya yayın için bir `CMutex` nesne, oluşturun bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesne ve çağrı kendi [kilit](../../mfc/reference/csinglelock-class.md#lock) ve [kilidini](../../mfc/reference/csinglelock-class.md#unlock) üye işlevleri. Varsa `CMutex` nesne kullanılan tek başına, çağrı kendi `Unlock` bunu serbest bırakmak için üye işlevi.

> [!IMPORTANT]
>  Oluşturduktan sonra `CMutex` nesnesi [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) mutex zaten yoktu emin olmak için. Mutex beklenmedik bir şekilde mevcut olması, dolandırıcı işlemin ele geçirilmesi ve mutex kötü amaçlı olarak kullanmayı planlayan gösterebilir. Bu durumda, tanıtıcı kapatın ve var olan bir hata varmış gibi nesnesi oluşturulurken devam etmek için önerilen güvenliğe yordam aynıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[CSyncObject Sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

