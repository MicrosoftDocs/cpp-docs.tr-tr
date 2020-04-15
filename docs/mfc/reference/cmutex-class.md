---
title: CMutex Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
ms.openlocfilehash: 2d6f637ab4828b3e70df205ebf359ae45a940d60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363278"
---
# <a name="cmutex-class"></a>CMutex Sınıfı

Bir "mutex" temsil eder - bir iş parçacığı bir kaynağa birbirini dışlayan erişim sağlayan bir eşitleme nesnesi.

## <a name="syntax"></a>Sözdizimi

```
class CMutex : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMutex::CMutex](#cmutex)|Bir `CMutex` nesne inşa eder.|

## <a name="remarks"></a>Açıklamalar

Mutexes bir seferde sadece bir iş parçacığı veri veya başka bir kontrollü kaynak değiştirmek için izin verilebiliyor yararlıdır. Örneğin, bağlı bir listeye düğüm eklemek, aynı anda yalnızca bir iş parçacığı tarafından izin verilmesi gereken bir işlemdir. Bağlı listeyi denetlemek için bir `CMutex` nesne kullanarak, bir defada yalnızca bir iş parçacığı listeye erişebilir.

Bir `CMutex` nesneyi kullanmak `CMutex` için gerektiğinde nesneyi oluşturun. Beklemek istediğiniz mutex'in adını belirtin ve uygulamanızın başlangıçta bu mutex'e sahip olması gerektiğini belirtin. Daha sonra oluşturucu döndüğünde mutex erişebilirsiniz. [CSyncObject'i arayın::Denetlenen](../../mfc/reference/csyncobject-class.md#unlock) kaynağa erişmeniz bittiğinde kilidini açın.

Nesneleri kullanmak `CMutex` için alternatif bir yöntem, denetlemek `CMutex` istediğiniz sınıfa veri üyesi olarak bir tür değişkeni eklemektir. Denetlenmiş nesnenin yapımı sırasında, mutex'in başlangıçta sahip olup olmadığını, mutex'in adını (işlem sınırları içinde kullanılacaksa) ve istenen güvenlik özniteliklerini belirten `CMutex` veri üyesinin oluşturucuyu arayın.

Nesneler tarafından `CMutex` bu şekilde denetlenir kaynaklara erişmek için, öncelikle kaynağınızın erişim üyesi işlevinde [CSingleLock](../../mfc/reference/csinglelock-class.md) türünden veya [CMultiLock](../../mfc/reference/cmultilock-class.md) türünden bir değişken oluşturun. Ardından kilit nesnesinin `Lock` üye işlevini arayın (örneğin, [CSingleLock::Lock).](../../mfc/reference/csinglelock-class.md#lock) Bu noktada, iş parçacığınız kaynağa erişebilir, kaynağın serbest bırakılmasını ve erişim kazanmasını bekler veya kaynağa erişemeyen kaynağın serbest bırakılmasını ve zaman alamasını bekler. Her durumda, kaynağınıza iş parçacığı güvenli bir şekilde erişildi. Kaynağı serbest bırakmak için kilit nesnesinin `Unlock` üye işlevini (örneğin, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)) kullanın veya kilit nesnesinin kapsam dışına düşmesine izin verin.

Nesneleri kullanma `CMutex` hakkında daha fazla bilgi için, [bkz.](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CMutex`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmt.h

## <a name="cmutexcmutex"></a><a name="cmutex"></a>CMutex::CMutex

Adlandırılmış veya adsız `CMutex` bir nesne oluşturuyor.

```
CMutex(
    BOOL bInitiallyOwn = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>Parametreler

*bInitiallyOwnOwn*<br/>
Nesneyi oluşturan iş parçacığının `CMutex` başlangıçta mutex tarafından denetlenir kaynağa erişimi olup olmadığını belirtir.

*Lpszname*<br/>
Nesnenin `CMutex` adı. Aynı ada sahip başka bir mutex varsa, nesne işlem sınırları boyunca *kullanılacaksa lpszName* sağlanmalıdır. **NULL**ise, mutex isimsiz olacaktır. Ad varolan bir mutex eşleşirse, `CMutex` oluşturucu bu adın mutex başvurulan yeni bir nesne oluşturur. Ad, mutex olmayan varolan bir eşitleme nesnesi ile eşleşirse, yapı başarısız olur.

*lpsaAttribute*<br/>
Mutex nesnesi için güvenlik öznitelikleri. Bu yapının tam açıklaması için Windows SDK'daki [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bakın.

### <a name="remarks"></a>Açıklamalar

Bir `CMutex` nesneye erişmek veya serbest bırakmak için bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturun ve [kilitle](../../mfc/reference/csinglelock-class.md#lock) ve [kilidini](../../mfc/reference/csinglelock-class.md#unlock) aç üye işlevlerini arayın. `CMutex` Nesne tek başına kullanılıyorsa, onu `Unlock` serbest bırakmak için üye işlevini arayın.

> [!IMPORTANT]
> Nesneyi `CMutex` oluşturduktan sonra, mutex'in zaten var olmadığından emin olmak için [GetLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) kullanın. Mutex beklenmedik bir şekilde var olsaydı, bir haydut süreci çömelme olduğunu gösterebilir ve kötü niyetli mutex kullanmak niyetinde olabilir. Bu durumda, önerilen güvenlik bilinçli yordamı tutamacı kapatmak ve nesne oluştururken bir hata var gibi devam etmektir.

## <a name="see-also"></a>Ayrıca bkz.

[CSyncObject Sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
