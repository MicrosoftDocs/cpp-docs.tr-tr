---
description: 'Daha fazla bilgi edinin: Csemafor sınıfı'
title: Csemafor sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
helpviewer_keywords:
- CSemaphore [MFC], CSemaphore
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
ms.openlocfilehash: 102b7ac9d7f934e3a04783c9ab537a858541c780
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264706"
---
# <a name="csemaphore-class"></a>Csemafor sınıfı

`CSemaphore`Bir veya daha fazla işlemde sınırlı sayıda iş parçacığına izin veren bir eşitleme nesnesi, bir veya daha fazla işlemde belirli bir kaynağa erişen iş parçacığı sayısı sayısını korur bir "semafor" temsil eder.

## <a name="syntax"></a>Syntax

```
class CSemaphore : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Csemafor:: Csemafor](#csemaphore)|Bir `CSemaphore` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Semaforlar yalnızca sınırlı sayıda kullanıcıyı destekleyebilen paylaşılan bir kaynağa erişimi denetlemek için faydalıdır. Nesnenin geçerli sayısı `CSemaphore` izin verilen ek kullanıcı sayısıdır. Sayı sıfıra ulaştığında, nesne tarafından denetlenen kaynağı kullanmaya yönelik tüm girişimler `CSemaphore` bir sistem kuyruğuna eklenir ve zaman aşımına uğrar ya da sayı 0 ' dan fazla olacak şekilde bekler. Denetlenen kaynağa tek seferde erişebilen en fazla kullanıcı sayısı, nesne oluşturma sırasında belirtilir `CSemaphore` .

Bir nesne kullanmak için `CSemaphore` , `CSemaphore` gerektiğinde nesneyi oluşturun. Beklemek istediğiniz semaforun adını belirtin ve uygulamanızın başlangıçta sahip olması gerekir. Ardından, Oluşturucu döndüğünde semafora erişebilirsiniz. Denetlenen kaynağa erişmeyi bitirdiğinizde [CSyncObject:: unlock](../../mfc/reference/csyncobject-class.md#unlock) öğesini çağırın.

Nesneleri kullanmak için alternatif bir yöntem `CSemaphore` , `CSemaphore` denetlemek istediğiniz sınıfa bir veri üyesi olarak türünde bir değişken eklemektir. Denetlenen nesnenin oluşturulması sırasında, `CSemaphore` ilk erişim sayısını, en fazla erişim sayısını, semaforun adını (işlem sınırları genelinde kullanılacaksa) ve istenen güvenlik özniteliklerini belirten veri üyesinin oluşturucusunu çağırın.

Bu şekilde nesnelere göre denetlenen kaynaklara erişmek için `CSemaphore` , önce [CSingleLock](../../mfc/reference/csinglelock-class.md) türünden bir değişken oluşturun ya da kaynağınızın erişim üyesi Işlevinizde [CMultiLock](../../mfc/reference/cmultilock-class.md) yazın. Ardından, Lock nesnesinin `Lock` üye işlevini çağırın (örneğin, [CSingleLock:: Lock](../../mfc/reference/csinglelock-class.md#lock)). Bu noktada, iş parçacığlarınız kaynağa erişim kazanacaktır, kaynağın serbest bırakılacağını ve erişim kazanmasını ya da kaynağın serbest bırakılacağını ve zaman aşımına gelmesini bekleyip kaynağa erişim elde edemeyecektir. Herhangi bir durumda, kaynağınız iş parçacığı güvenli bir şekilde erişilir. Kaynağı serbest bırakmak için, Lock nesnesinin `Unlock` üye işlevini kullanın (örneğin, [CSingleLock:: unlock](../../mfc/reference/csinglelock-class.md#unlock)) veya kilit nesnesinin kapsam dışına çıkmasına izin verin.

Alternatif olarak, bir `CSemaphore` nesnesi tek başına oluşturabilir ve denetimli kaynağa erişmeyi denemeden önce açık olarak erişebilirsiniz. Bu yöntem, kaynak kodunuzu okuyan birisinin daha açık olması durumunda hataya açıktır.

Nesneleri kullanma hakkında daha fazla bilgi için `CSemaphore` bkz. [Çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CSemaphore`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt. h

## <a name="csemaphorecsemaphore"></a><a name="csemaphore"></a> Csemafor:: Csemafor

Adlandırılmış veya adlandırılmamış bir `CSemaphore` nesne oluşturur.

```
CSemaphore(
    LONG lInitialCount = 1,
    LONG lMaxCount = 1,
    LPCTSTR pstrName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```

### <a name="parameters"></a>Parametreler

*lInitialCount*<br/>
Semaforun başlangıçtaki kullanım sayısı. 0 ' dan büyük veya buna eşit ve *lMaxCount* değerinden küçük veya buna eşit olmalıdır.

*lMaxCount*<br/>
Semafor için en yüksek kullanım sayısı. 0 ' dan büyük olmalıdır.

*pstrName*<br/>
Semaforun adı. Semaforun işlem sınırları genelinde erişilmesi durumunda bu sağlanmalıdır. İse `NULL` , nesne adlandırılmamış olur. Ad mevcut bir semafora eşleşiyorsa, Oluşturucu `CSemaphore` Bu adın semaforuna başvuran yeni bir nesne oluşturur. Ad, semafor olmayan mevcut bir eşitleme nesnesiyle eşleşiyorsa, oluşturma başarısız olur.

*lpsaAttributes*<br/>
Semafor nesnesi için güvenlik öznitelikleri. Bu yapının tam açıklaması için Windows SDK [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bakın.

### <a name="remarks"></a>Açıklamalar

Bir nesneye erişmek veya onu serbest bırakmak için `CSemaphore` bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturun ve [Lock](../../mfc/reference/csinglelock-class.md#lock) ve [unlock](../../mfc/reference/csinglelock-class.md#unlock) üye işlevlerini çağırın.

> [!IMPORTANT]
> Nesneyi oluşturduktan sonra `CSemaphore` , mutex ' [](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) i kullanarak mutex 'in zaten mevcut olmadığından emin olun. Mutex beklenmedik bir şekilde mevcutsa, bir standart dışı işlemin ele geçirilmesi gerektiğini belirtebilir ve mutex 'i kötü amaçlı olarak kullanmak için bu olabilir. Bu durumda, önerilen güvenlik bilincine sahip yordam, tanıtıcıyı kapatmak ve nesneyi oluştururken bir hata olması gibi devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[CSyncObject sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
