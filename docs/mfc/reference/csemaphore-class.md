---
title: CSemaphore Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
ms.openlocfilehash: 26e1fd55d321b221f4732874d57d02a79c4c6398
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318507"
---
# <a name="csemaphore-class"></a>CSemaphore Sınıfı

Sınıfın `CSemaphore` bir nesnesi bir "semaphore" temsil eder - bir veya daha fazla işlemde sınırlı sayıda iş parçacığı nın erişmesine izin veren bir eşitleme nesnesi, şu anda belirli bir kaynağa erişen iş parçacığı sayısının sayısını korur.

## <a name="syntax"></a>Sözdizimi

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSemaphore::CSemaphore](#csemaphore)|Bir `CSemaphore` nesne inşa eder.|

## <a name="remarks"></a>Açıklamalar

Semaforlar, yalnızca sınırlı sayıda kullanıcıyı desteklenebilen paylaşılan bir kaynağa erişimi denetlemede yararlıdır. Nesnenin `CSemaphore` geçerli sayısı, izin verilen ek kullanıcı sayısıdır. Sayım sıfıra ulaştığında, `CSemaphore` nesne tarafından denetlenen kaynağı kullanmaya yönelik tüm denemeler bir sistem kuyruğuna eklenir ve zaman ları bitene veya sayım 0'ın üzerine çıkana kadar bekler. Nesnenin yapımı `CSemaphore` sırasında denetitilen kaynağa aynı anda erişebilen maksimum kullanıcı sayısı belirtilir.

Bir `CSemaphore` nesneyi kullanmak `CSemaphore` için gerektiğinde nesneyi oluşturun. Beklemek istediğiniz semaforun adını belirtin ve uygulamanızın başlangıçta bu fişe sahip olması gerektiğini belirtin. Daha sonra konstrüktör döndüğünde semafora erişebilirsiniz. [CSyncObject'i arayın::Denetlenen](../../mfc/reference/csyncobject-class.md#unlock) kaynağa erişmeniz bittiğinde kilidini açın.

Nesneleri kullanmak `CSemaphore` için alternatif bir yöntem, denetlemek `CSemaphore` istediğiniz sınıfa veri üyesi olarak bir tür değişkeni eklemektir. Denetlenmiş nesnenin yapımı sırasında, ilk `CSemaphore` erişim sayısını, maksimum erişim sayısını, semaforun adını (işlem sınırları içinde kullanılacaksa) ve istenen güvenlik özniteliklerini belirten veri üyesinin oluşturucuyu arayın.

Nesneler tarafından `CSemaphore` bu şekilde denetlenir kaynaklara erişmek için, öncelikle kaynağınızın erişim üyesi işlevinde [CSingleLock](../../mfc/reference/csinglelock-class.md) türünden veya [CMultiLock](../../mfc/reference/cmultilock-class.md) türünden bir değişken oluşturun. Ardından kilit nesnesinin `Lock` üye işlevini arayın (örneğin, [CSingleLock::Lock).](../../mfc/reference/csinglelock-class.md#lock) Bu noktada, iş parçacığınız kaynağa erişebilir, kaynağın serbest bırakılmasını ve erişim kazanmasını bekler veya kaynağa erişemeyen kaynağın serbest bırakılmasını ve zaman alamasını bekler. Her durumda, kaynağınıza iş parçacığı güvenli bir şekilde erişildi. Kaynağı serbest bırakmak için kilit nesnesinin `Unlock` üye işlevini (örneğin, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)) kullanın veya kilit nesnesinin kapsam dışına düşmesine izin verin.

Alternatif olarak, tek `CSemaphore` başına bir nesne oluşturabilir ve denetitilen kaynağa erişmeye çalışmadan önce bu nesneye açıkça erişebilirsiniz. Bu yöntem, kaynak kodunuzu okuyan biri için daha net olsa da, hataya daha yatkındır.

Nesnelerin nasıl kullanılacağı `CSemaphore` hakkında daha fazla bilgi için [Multithreading: Synchronization Classes nasıl kullanılır makalesine](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmt.h

## <a name="csemaphorecsemaphore"></a><a name="csemaphore"></a>CSemaphore::CSemaphore

Adlandırılmış veya adsız `CSemaphore` bir nesne oluşturuyor.

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>Parametreler

*lInitialCount*<br/>
Semafor için ilk kullanım sayısı. 0'dan büyük veya eşit ve *lMaxCount'dan*daha az veya eşit olmalıdır.

*lMaxCount*<br/>
Semafor için maksimum kullanım sayısı. 0'dan büyük olmalı.

*pstrName*<br/>
Semaforun adı. Semafora süreç sınırları boyunca erişilecekse sağlanmalıdır. Eğer, `NULL`nesne adsız olacaktır. Ad varolan bir semaforla eşleşirse, `CSemaphore` oluşturucu bu ismin semaforuna başvuran yeni bir nesne oluşturur. Ad semafor olmayan varolan bir eşitleme nesnesi ile eşleşirse, yapı başarısız olur.

*lpsaAttributes*<br/>
Semafor nesnesi için güvenlik öznitelikleri. Bu yapının tam açıklaması için Windows SDK'daki [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bakın.

### <a name="remarks"></a>Açıklamalar

Bir `CSemaphore` nesneye erişmek veya serbest bırakmak için bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturun ve [kilitle](../../mfc/reference/csinglelock-class.md#lock) ve [kilidini](../../mfc/reference/csinglelock-class.md#unlock) aç üye işlevlerini arayın.

> [!IMPORTANT]
> Nesneyi `CSemaphore` oluşturduktan sonra, mutex'in zaten var olmadığından emin olmak için [GetLastError'ı](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) kullanın. Mutex beklenmedik bir şekilde var olsaydı, bir haydut süreci çömelme olduğunu gösterebilir ve kötü niyetli mutex kullanmak niyetinde olabilir. Bu durumda, önerilen güvenlik bilinçli yordamı tutamacı kapatmak ve nesne oluştururken bir hata var gibi devam etmektir.

## <a name="see-also"></a>Ayrıca bkz.

[CSyncObject Sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
