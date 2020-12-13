---
description: 'Daha fazla bilgi edinin: CMutex sınıfı'
title: CMutex sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMutex
- AFXMT/CMutex
- AFXMT/CMutex::CMutex
helpviewer_keywords:
- CMutex [MFC], CMutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
ms.openlocfilehash: 4890a99d52fb8142bac0cc25d6a23ef6dbcaed5b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331497"
---
# <a name="cmutex-class"></a>CMutex sınıfı

Bir iş parçacığının bir kaynağa birbirini dışlamalı erişimine izin veren bir eşitleme nesnesi olan bir "mutex" temsil eder.

## <a name="syntax"></a>Syntax

```
class CMutex : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMutex:: CMutex](#cmutex)|Bir `CMutex` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Tek seferde yalnızca bir iş parçacığının verileri veya diğer denetlenen kaynakları değiştirmesine izin verildiğinde, zaman uyumu sağlayıcılar yararlı olur. Örneğin, bağlantılı bir listeye düğüm eklemek, tek seferde yalnızca bir iş parçacığı tarafından izin verilmesi gereken bir işlemdir. `CMutex`Bağlantılı listeyi denetlemek için bir nesne kullanarak, aynı anda yalnızca bir iş parçacığı listeye erişim sağlayabilir.

Bir nesne kullanmak için `CMutex` , `CMutex` gerektiğinde nesneyi oluşturun. Beklemek istediğiniz mutex 'in adını belirtin ve uygulamanızın başlangıçta sahip olması gerekir. Ardından, Oluşturucu döndüğünde mutex 'e erişebilirsiniz. Denetlenen kaynağa erişmeyi bitirdiğinizde [CSyncObject:: unlock](../../mfc/reference/csyncobject-class.md#unlock) öğesini çağırın.

Nesneleri kullanmak için alternatif bir yöntem `CMutex` , `CMutex` denetlemek istediğiniz sınıfa bir veri üyesi olarak türünde bir değişken eklemektir. Denetlenen nesnenin oluşturulması sırasında, `CMutex` mutex 'in başlangıçta sahip olup olmadığını belirten veri üyesinin oluşturucusunu, mutex 'in adını (işlem sınırları boyunca kullanılacaksa) ve istenen güvenlik özniteliklerini çağırın.

Bu şekilde nesnelere göre denetlenen kaynaklara erişmek için `CMutex` , önce [CSingleLock](../../mfc/reference/csinglelock-class.md) türünden bir değişken oluşturun ya da kaynağınızın erişim üyesi Işlevinizde [CMultiLock](../../mfc/reference/cmultilock-class.md) yazın. Ardından, Lock nesnesinin `Lock` üye işlevini çağırın (örneğin, [CSingleLock:: Lock](../../mfc/reference/csinglelock-class.md#lock)). Bu noktada, iş parçacığlarınız kaynağa erişim kazanacaktır, kaynağın serbest bırakılacağını ve erişim kazanmasını ya da kaynağın serbest bırakılacağını ve zaman aşımına gelmesini bekleyip kaynağa erişim elde edemeyecektir. Herhangi bir durumda, kaynağınız iş parçacığı güvenli bir şekilde erişilir. Kaynağı serbest bırakmak için, Lock nesnesinin `Unlock` üye işlevini kullanın (örneğin, [CSingleLock:: unlock](../../mfc/reference/csinglelock-class.md#unlock)) veya kilit nesnesinin kapsam dışına çıkmasına izin verin.

Nesneleri kullanma hakkında daha fazla bilgi için `CMutex` bkz. [Çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CMutex`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt. h

## <a name="cmutexcmutex"></a><a name="cmutex"></a> CMutex:: CMutex

Adlandırılmış veya adlandırılmamış bir `CMutex` nesne oluşturur.

```
CMutex(
    BOOL bInitiallyOwn = FALSE,
    LPCTSTR lpszName = NULL,
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```

### <a name="parameters"></a>Parametreler

*Biniyown*<br/>
Nesneyi oluşturan iş parçacığının `CMutex` başlangıçta mutex tarafından denetlenen kaynağa erişip erişemediğini belirtir.

*lpszName*<br/>
`CMutex`Nesnenin adı. Aynı ada sahip başka bir mutex varsa, nesne işlem sınırları genelinde kullanılacaksa *lpszName* sağlanması gerekir. **Null** ise mutex adlandırılmamış olur. Ad mevcut bir mutex ile eşleşiyorsa, Oluşturucu `CMutex` Bu adın mutex 'ine başvuran yeni bir nesne oluşturur. Ad, mutex olmayan mevcut bir eşitleme nesnesiyle eşleşiyorsa, oluşturma başarısız olur.

*lpsaAttribute*<br/>
Mutex nesnesi için güvenlik öznitelikleri. Bu yapının tam açıklaması için Windows SDK [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bakın.

### <a name="remarks"></a>Açıklamalar

Bir nesneye erişmek veya onu serbest bırakmak için `CMutex` bir [CMultiLock](../../mfc/reference/cmultilock-class.md) veya [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturun ve [Lock](../../mfc/reference/csinglelock-class.md#lock) ve [unlock](../../mfc/reference/csinglelock-class.md#unlock) üye işlevlerini çağırın. `CMutex`Nesne tek başına kullanılıyorsa, `Unlock` serbest bırakmak için üye işlevini çağırın.

> [!IMPORTANT]
> Nesneyi oluşturduktan sonra `CMutex` , mutex ' [](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) i kullanarak mutex 'in zaten mevcut olmadığından emin olun. Mutex beklenmedik bir şekilde mevcutsa, bir standart dışı işlemin ele geçirilmesi gerektiğini belirtebilir ve mutex 'i kötü amaçlı olarak kullanmak için bu olabilir. Bu durumda, önerilen güvenlik bilincine sahip yordam, tanıtıcıyı kapatmak ve nesneyi oluştururken bir hata olması gibi devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[CSyncObject sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
