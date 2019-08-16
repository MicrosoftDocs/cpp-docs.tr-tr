---
title: Csemafor sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
ms.openlocfilehash: d5a0e4187107aaab7cedf4e7a0e2fc47b9f9f305
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502576"
---
# <a name="csemaphore-class"></a>Csemafor sınıfı

Bir veya daha fazla işlemde sınırlı sayıda iş parçacığına izin veren bir eşitleme nesnesi, bir veya daha fazla işlemde belirli bir kaynağa erişen iş parçacığı sayısı sayısını korur bir "semafor" temsileder.`CSemaphore`

## <a name="syntax"></a>Sözdizimi

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Csemafor:: Csemafor](#csemaphore)|Bir `CSemaphore` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Semaforlar yalnızca sınırlı sayıda kullanıcıyı destekleyebilen paylaşılan bir kaynağa erişimi denetlemek için faydalıdır. `CSemaphore` Nesnenin geçerli sayısı izin verilen ek kullanıcı sayısıdır. Sayı sıfıra ulaştığında, `CSemaphore` nesne tarafından denetlenen kaynağı kullanmaya yönelik tüm girişimler bir sistem kuyruğuna eklenir ve zaman aşımına uğrar ya da sayı 0 ' dan fazla olacak şekilde bekler. Denetlenen kaynağa tek seferde erişebilen en fazla kullanıcı sayısı, `CSemaphore` nesne oluşturma sırasında belirtilir.

Bir `CSemaphore` nesne kullanmak için, gerektiğinde `CSemaphore` nesneyi oluşturun. Beklemek istediğiniz semaforun adını belirtin ve uygulamanızın başlangıçta sahip olması gerekir. Ardından, Oluşturucu döndüğünde semafora erişebilirsiniz. Denetlenen kaynağa erişmeyi bitirdiğinizde [CSyncObject:: unlock](../../mfc/reference/csyncobject-class.md#unlock) öğesini çağırın.

Nesneleri kullanmak `CSemaphore` için alternatif bir yöntem, denetlemek istediğiniz sınıfa bir veri üyesi `CSemaphore` olarak türünde bir değişken eklemektir. Denetlenen nesnenin oluşturulması sırasında, ilk erişim sayısını, en fazla erişim `CSemaphore` sayısını, semaforun adını (işlem sınırları genelinde kullanılacaksa) ve istenen güvenlik özniteliklerini belirten veri üyesinin oluşturucusunu çağırın.

Bu şekilde nesnelere göre `CSemaphore` denetlenen kaynaklara erişmek için, önce [CSingleLock](../../mfc/reference/csinglelock-class.md) türünden bir değişken oluşturun ya da kaynağınızın erişim üyesi işlevinizde [CMultiLock](../../mfc/reference/cmultilock-class.md) yazın. Ardından, Lock nesnesinin `Lock` üye işlevini çağırın (örneğin, [CSingleLock:: Lock](../../mfc/reference/csinglelock-class.md#lock)). Bu noktada, iş parçacığlarınız kaynağa erişim kazanacaktır, kaynağın serbest bırakılacağını ve erişim kazanmasını ya da kaynağın serbest bırakılacağını ve zaman aşımına gelmesini bekleyip kaynağa erişim elde edemeyecektir. Herhangi bir durumda, kaynağınız iş parçacığı güvenli bir şekilde erişilir. Kaynağı serbest bırakmak için, Lock nesnesinin `Unlock` üye işlevini kullanın (örneğin, [CSingleLock:: unlock](../../mfc/reference/csinglelock-class.md#unlock)) veya kilit nesnesinin kapsam dışına çıkmasına izin verin.

Alternatif olarak, bir `CSemaphore` nesnesi tek başına oluşturabilir ve denetimli kaynağa erişmeyi denemeden önce açık olarak erişebilirsiniz. Bu yöntem, kaynak kodunuzu okuyan birisinin daha açık olması durumunda hataya açıktır.

Nesneleri kullanma `CSemaphore` hakkında daha fazla bilgi için çoklu iş parçacığı oluşturma makalesine [bakın: Eşitleme sınıflarını](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)kullanma.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt. h

##  <a name="csemaphore"></a>Csemafor:: Csemafor

Adlandırılmış veya adlandırılmamış `CSemaphore` bir nesne oluşturur.

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>Parametreler

*lInitialCount*<br/>
Semaforun başlangıçtaki kullanım sayısı. 0 ' dan büyük veya buna eşit ve *lMaxCount*değerinden küçük veya buna eşit olmalıdır.

*lMaxCount*<br/>
Semafor için en yüksek kullanım sayısı. 0 ' dan büyük olmalıdır.

*pstrName*<br/>
Semaforun adı. Semaforun işlem sınırları genelinde erişilmesi durumunda bu sağlanmalıdır. İse `NULL`, nesne adlandırılmamış olur. Ad mevcut bir semafora eşleşiyorsa, Oluşturucu bu adın semaforuna başvuran `CSemaphore` yeni bir nesne oluşturur. Ad, semafor olmayan mevcut bir eşitleme nesnesiyle eşleşiyorsa, oluşturma başarısız olur.

*lpsaAttributes*<br/>
Semafor nesnesi için güvenlik öznitelikleri. Bu yapının tam açıklaması için Windows SDK [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bakın.

### <a name="remarks"></a>Açıklamalar

Bir `CSemaphore` nesneye erişmek veya onu serbest bırakmak için bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturun ve [Lock](../../mfc/reference/csinglelock-class.md#lock) ve [unlock](../../mfc/reference/csinglelock-class.md#unlock) üye işlevlerini çağırın.

> [!IMPORTANT]
>  Nesneyi oluşturduktan sonra, mutex ' i kullanarak mutex 'in zaten mevcut olmadığından emin olun. [](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) `CSemaphore` Mutex beklenmedik bir şekilde mevcutsa, bir standart dışı işlemin ele geçirilmesi gerektiğini belirtebilir ve mutex 'i kötü amaçlı olarak kullanmak için bu olabilir. Bu durumda, önerilen güvenlik bilincine sahip yordam, tanıtıcıyı kapatmak ve nesneyi oluştururken bir hata olması gibi devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[CSyncObject Sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
