---
title: CMutex sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
ms.openlocfilehash: 65f7f4db9489de1c9a380d760ed5cab41bfdc2ec
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504515"
---
# <a name="cmutex-class"></a>CMutex sınıfı

Bir iş parçacığının bir kaynağa birbirini dışlamalı erişimine izin veren bir eşitleme nesnesi olan bir "mutex" temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMutex : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMutex:: CMutex](#cmutex)|Bir `CMutex` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Tek seferde yalnızca bir iş parçacığının verileri veya diğer denetlenen kaynakları değiştirmesine izin verildiğinde, zaman uyumu sağlayıcılar yararlı olur. Örneğin, bağlantılı bir listeye düğüm eklemek, tek seferde yalnızca bir iş parçacığı tarafından izin verilmesi gereken bir işlemdir. Bağlantılı listeyi denetlemek `CMutex` için bir nesne kullanarak, aynı anda yalnızca bir iş parçacığı listeye erişim sağlayabilir.

Bir `CMutex` nesne kullanmak için, gerektiğinde `CMutex` nesneyi oluşturun. Beklemek istediğiniz mutex 'in adını belirtin ve uygulamanızın başlangıçta sahip olması gerekir. Ardından, Oluşturucu döndüğünde mutex 'e erişebilirsiniz. Denetlenen kaynağa erişmeyi bitirdiğinizde [CSyncObject:: unlock](../../mfc/reference/csyncobject-class.md#unlock) öğesini çağırın.

Nesneleri kullanmak `CMutex` için alternatif bir yöntem, denetlemek istediğiniz sınıfa bir veri üyesi `CMutex` olarak türünde bir değişken eklemektir. Denetlenen nesnenin oluşturulması sırasında, mutex 'in başlangıçta sahip olup olmadığını belirten `CMutex` veri üyesinin oluşturucusunu, mutex 'in adını (işlem sınırları boyunca kullanılacaksa) ve istenen güvenlik özniteliklerini çağırın.

Bu şekilde nesnelere göre `CMutex` denetlenen kaynaklara erişmek için, önce [CSingleLock](../../mfc/reference/csinglelock-class.md) türünden bir değişken oluşturun ya da kaynağınızın erişim üyesi işlevinizde [CMultiLock](../../mfc/reference/cmultilock-class.md) yazın. Ardından, Lock nesnesinin `Lock` üye işlevini çağırın (örneğin, [CSingleLock:: Lock](../../mfc/reference/csinglelock-class.md#lock)). Bu noktada, iş parçacığlarınız kaynağa erişim kazanacaktır, kaynağın serbest bırakılacağını ve erişim kazanmasını ya da kaynağın serbest bırakılacağını ve zaman aşımına gelmesini bekleyip kaynağa erişim elde edemeyecektir. Herhangi bir durumda, kaynağınız iş parçacığı güvenli bir şekilde erişilir. Kaynağı serbest bırakmak için, Lock nesnesinin `Unlock` üye işlevini kullanın (örneğin, [CSingleLock:: unlock](../../mfc/reference/csinglelock-class.md#unlock)) veya kilit nesnesinin kapsam dışına çıkmasına izin verin.

Nesneleri kullanma `CMutex` hakkında daha fazla bilgi için çoklu iş parçacığı [oluşturma makalesine bakın: Eşitleme sınıflarını](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)kullanma.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CMutex`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt. h

##  <a name="cmutex"></a>CMutex:: CMutex

Adlandırılmış veya adlandırılmamış `CMutex` bir nesne oluşturur.

```
CMutex(
    BOOL bInitiallyOwn = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>Parametreler

*Biniyown*<br/>
`CMutex` Nesneyi oluşturan iş parçacığının başlangıçta mutex tarafından denetlenen kaynağa erişip erişemediğini belirtir.

*lpszName*<br/>
`CMutex` Nesnenin adı. Aynı ada sahip başka bir mutex varsa, nesne işlem sınırları genelinde kullanılacaksa *lpszName* sağlanması gerekir. **Null**ise mutex adlandırılmamış olur. Ad mevcut bir mutex ile eşleşiyorsa, Oluşturucu bu adın mutex 'ine başvuran `CMutex` yeni bir nesne oluşturur. Ad, mutex olmayan mevcut bir eşitleme nesnesiyle eşleşiyorsa, oluşturma başarısız olur.

*lpsaAttribute*<br/>
Mutex nesnesi için güvenlik öznitelikleri. Bu yapının tam açıklaması için Windows SDK [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bakın.

### <a name="remarks"></a>Açıklamalar

Bir `CMutex` nesneye erişmek veya onu serbest bırakmak için bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturun ve [Lock](../../mfc/reference/csinglelock-class.md#lock) ve [unlock](../../mfc/reference/csinglelock-class.md#unlock) üye işlevlerini çağırın. Nesne tek başına kullanılıyorsa, serbest bırakmak için `Unlock` üye işlevini çağırın. `CMutex`

> [!IMPORTANT]
>  Nesneyi oluşturduktan sonra, mutex ' i kullanarak mutex 'in zaten mevcut olmadığından emin olun. [](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) `CMutex` Mutex beklenmedik bir şekilde mevcutsa, bir standart dışı işlemin ele geçirilmesi gerektiğini belirtebilir ve mutex 'i kötü amaçlı olarak kullanmak için bu olabilir. Bu durumda, önerilen güvenlik bilincine sahip yordam, tanıtıcıyı kapatmak ve nesneyi oluştururken bir hata olması gibi devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[CSyncObject Sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
