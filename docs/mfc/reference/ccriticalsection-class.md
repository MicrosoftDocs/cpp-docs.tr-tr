---
title: Sezaryen Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCriticalSection
- AFXMT/CCriticalSection
- AFXMT/CCriticalSection::CCriticalSection
- AFXMT/CCriticalSection::Lock
- AFXMT/CCriticalSection::Unlock
- AFXMT/CCriticalSection::m_sect
helpviewer_keywords:
- CCriticalSection [MFC], CCriticalSection
- CCriticalSection [MFC], Lock
- CCriticalSection [MFC], Unlock
- CCriticalSection [MFC], m_sect
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
ms.openlocfilehash: d79199a332f6930619e6b4995b04bc590b6ea580
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369371"
---
# <a name="ccriticalsection-class"></a>Sezaryen Sınıfı

Bir "kritik bölümü" temsil eder — bir anda bir iş parçacığının bir kaynağa veya kod bölümüne erişmesine izin veren bir eşitleme nesnesi.

## <a name="syntax"></a>Sözdizimi

```
class CCriticalSection : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Karsiksiyon::Ccriticalsection](#ccriticalsection)|Bir `CCriticalSection` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Kritik Bölüm::Kilit](#lock)|`CCriticalSection` Nesneye erişmek için kullanın.|
|[CCriticalSection::Kilidini Aç](#unlock)|Nesneyi `CCriticalSection` serbest bırakır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CCriticalSection::operatör CRITICAL_SECTION*](#operator_critical_section_star)|İç CRITICAL_SECTION nesnesine bir işaretçi alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[Kars Bölümü::m_sect](#m_sect)|CRITICAL_SECTION bir nesne.|

## <a name="remarks"></a>Açıklamalar

Kritik bölümler, verileri veya başka bir denetimaltındaki kaynağı değiştirmek için aynı anda yalnızca bir iş parçacığına izin verildiğinde yararlıdır. Örneğin, bağlı bir listeye düğüm eklemek, aynı anda yalnızca bir iş parçacığı tarafından izin verilmesi gereken bir işlemdir. Bağlı listeyi denetlemek için bir `CCriticalSection` nesne kullanarak, bir defada yalnızca bir iş parçacığı listeye erişebilir.

> [!NOTE]
> `CCriticalSection` Sınıfın işlevselliği gerçek bir Win32 CRITICAL_SECTION nesnesi tarafından sağlanır.

Hız kritik olduğunda ve kaynak işlem sınırları boyunca kullanılmadığında mutexler yerine kritik kesitler kullanılır [(Bkz. CMutex).](../../mfc/reference/cmutex-class.md)

Bir `CCriticalSection` nesneyi kullanmak için iki yöntem vardır: tek başına ve bir sınıfa katıştirılmış.

- Tek başına yöntem Tek başına `CCriticalSection` bir nesne `CCriticalSection` kullanmak için gerektiğinde nesneyi oluşturun. Oluşturucudan başarılı bir dönüş ten sonra, nesneyi [Kilitle'ye](#lock)bir çağrıyla açık bir şekilde kilitleyin. Kritik bölüme erişmeyi bitirdiğinizde [Kilidini Aç'ı](#unlock) arayın. Bu yöntem, kaynak kodunuzu okuyan biri için daha net olmakla birlikte, erişimden önce ve sonra kritik bölümü kilitlemeyi ve kilidini açmayı unutmanız gerektiğinden hataya daha yatkındır.

   Daha tercih edilen bir yöntem [CSingleLock](../../mfc/reference/csinglelock-class.md) sınıfını kullanmaktır. Ayrıca bir `Lock` ve `Unlock` yöntemi vardır, ancak bir özel durum oluşursa kaynağın kilidini açma konusunda endişelenmenize gerek yoktur.

- Katışdırılmış yöntem Sınıfa bir `CCriticalSection`tür veri üyesi ekleyerek ve gerektiğinde veri üyesini kilitleyerek birden çok iş parçacığı yla bir sınıfı da paylaşabilirsiniz.

Nesneleri kullanma `CCriticalSection` hakkında daha fazla bilgi için, [bkz.](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmt.h

## <a name="ccriticalsectionccriticalsection"></a><a name="ccriticalsection"></a>Karsiksiyon::Ccriticalsection

Bir `CCriticalSection` nesne inşa eder.

```
CCriticalSection();
```

### <a name="remarks"></a>Açıklamalar

Bir `CCriticalSection` nesneye erişmek veya serbest bırakmak için bir [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturun ve üye işlevlerini [Kilitle](../../mfc/reference/csinglelock-class.md#lock) ve [Aç'ı](../../mfc/reference/csinglelock-class.md#unlock) çağırın. `CCriticalSection` Nesne tek başına kullanılıyorsa, onu serbest bırakmak için [Unlock](#unlock) üye işlevini arayın.

Oluşturucu gerekli sistem belleği ayırmak için başarısız olursa, bir bellek özel durum [(cMemoryException](../../mfc/reference/cmemoryexception-class.md)türü) otomatik olarak atılır.

### <a name="example"></a>Örnek

  CCriticalSection için örneğe [bakın:Kilitleyin.](#lock)

## <a name="ccriticalsectionlock"></a><a name="lock"></a>Kritik Bölüm::Kilit

Kritik bölüm nesnesine erişmek için bu üye işlevi arayın.

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>Parametreler

*dwTimeout*<br/>
`Lock`bu parametre değerini yoksa.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olduysa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`Lock`kritik bölüm nesnesi sinyal verilene (kullanılabilir hale gelene) kadar geri dönmeyecek bir engelleme çağrısıdır.

Zamanlanmış beklemeler gerekiyorsa, `CCriticalSection` nesne yerine Bir [CMutex](../../mfc/reference/cmutex-class.md) nesnesi kullanabilirsiniz.

Gerekli `Lock` sistem belleği tahsis ediútiriğinde değişen sağlık, [(CMemoryException](../../mfc/reference/cmemoryexception-class.md)türünün) bir bellek istisnası otomatik olarak atılır.

### <a name="example"></a>Örnek

Bu örnek, paylaşılan `_strShared` `CCriticalSection` bir nesneyi kullanarak paylaşılan kaynağa (statik nesne) erişimi denetleyerek iç içe geçmiş kritik bölüm yaklaşımını gösterir. İşlev, `SomeMethod` paylaşılan kaynağın güvenli bir şekilde güncelleştirilmesini gösterir.

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

## <a name="ccriticalsectionm_sect"></a><a name="m_sect"></a>Kars Bölümü::m_sect

Tüm `CCriticalSection` yöntemler tarafından kullanılan kritik bir bölüm nesnesi içerir.

```
CRITICAL_SECTION m_sect;
```

## <a name="ccriticalsectionoperator-critical_section"></a><a name="operator_critical_section_star"></a>CCriticalSection::operatör CRITICAL_SECTION*

CRITICAL_SECTION bir nesne alır.

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>Açıklamalar

İç CRITICAL_SECTION nesnesine işaretçi almak için bu işlevi çağırın.

## <a name="ccriticalsectionunlock"></a><a name="unlock"></a>CCriticalSection::Kilidini Aç

Nesneyi `CCriticalSection` başka bir iş parçacığı tarafından kullanılmak üzere serbest bırakır.

```
BOOL Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

`CCriticalSection` Nesne iş parçacığına aitse ve sürüm başarılı ysa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Tek `CCriticalSection` başına kullanılıyorsa, `Unlock` kritik bölüm tarafından kontrol edilen kaynağın kullanımı tamamlandıktan hemen sonra çağrılmalıdır. Bir [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi `CCriticalSection::Unlock` kullanılıyorsa, kilit nesnesinin `Unlock` üye işlevi tarafından çağrılır.

### <a name="example"></a>Örnek

  CCriticalSection için örneğe [bakın:Kilitleyin.](#lock)

## <a name="see-also"></a>Ayrıca bkz.

[CSyncObject Sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMutex Sınıfı](../../mfc/reference/cmutex-class.md)
