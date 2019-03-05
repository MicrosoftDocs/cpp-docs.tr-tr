---
title: CCriticalSection sınıfı
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
ms.openlocfilehash: 2c89647afc8a9a8c6564d25afe20d48818a643f2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291047"
---
# <a name="ccriticalsection-class"></a>CCriticalSection sınıfı

"Kritik bölüm" temsil eder; bir kaynağa veya kod bölümüne erişmek için bir seferde bir iş parçacığına izin veren bir eşitleme nesnesi.

## <a name="syntax"></a>Sözdizimi

```
class CCriticalSection : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CCriticalSection::CCriticalSection](#ccriticalsection)|Oluşturur bir `CCriticalSection` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CCriticalSection::Lock](#lock)|Erişim elde etmek için kullanmak `CCriticalSection` nesne.|
|[CCriticalSection::Unlock](#unlock)|Yayınları `CCriticalSection` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|İç CRITICAL_SECTION nesneye bir işaretçi alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CCriticalSection::m_sect](#m_sect)|Bir CRITICAL_SECTION nesnesi.|

## <a name="remarks"></a>Açıklamalar

Kritik bölümler, veri veya denetlenen başka bir kaynak değiştirmek için aynı anda yalnızca tek bir iş parçacığı izin verildiğinde kullanışlıdır. Örneğin, bağlı bir liste düğüm ekleme, yalnızca tek bir iş parçacığı tarafından aynı anda izin verilmesi, bir işlemdir. Kullanarak bir `CCriticalSection` öbekleri bağlantılı listede aynı anda tek bir iş parçacığı listesine ulaşmak yalnızca denetlemek için nesne.

> [!NOTE]
>  İşlevselliğini `CCriticalSection` sınıfı gerçek Win32 CRITICAL_SECTION nesne tarafından sağlanır.

Kritik bölümler, mutex'leri yerine kullanılır (bkz [CMutex](../../mfc/reference/cmutex-class.md)) olduğunda hızı kritik ve kaynak arasında işlem sınırları kullanılmayacak.

Kullanmak için iki farklı yöntemle bir `CCriticalSection` nesne: tek başına ve katıştırılmış bir sınıf.

- Tek başına kullanılan tek başına yöntem `CCriticalSection` nesne, oluşturmak `CCriticalSection` gerektiğinde nesne. Sonra başarılı bir dönüş oluşturucudan açıkça çağrısıyla nesneyi kilitlemek [kilit](#lock). Çağrı [kilidini](#unlock) işiniz bittiğinde kritik bölüm erişme. Bu, kaynak kodunuzu okuyan kişi daha anlaşılır sırasında kilitlemek ve kritik bölüm önce ve sonra erişim kilidini açmak hatırlamalısınız gibi daha fazla hataya yöntemidir.

   Daha fazla tercih edilen bir yöntem kullanmaktır [CSingleLock](../../mfc/reference/csinglelock-class.md) sınıfı. Ayrıca bir `Lock` ve `Unlock` yöntemi, ancak bir özel durum oluşursa, kaynağın kilidini açma hakkında endişe etmeniz gerekmez.

- Yöntemi de paylaşabilirsiniz bir sınıf ile birden çok iş parçacığı ekleyerek katıştırılmış bir `CCriticalSection`-türü veri üyesi sınıfı ve gerektiğinde veri üyesi kilitleme.

Kullanma hakkında daha fazla bilgi için `CCriticalSection` nesneleri başlıklı makaleye bakın [çoklu iş parçacığı kullanımı: Eşitleme sınıflarının nasıl kullanılacağını](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt.h

##  <a name="ccriticalsection"></a>  CCriticalSection::CCriticalSection

Oluşturur bir `CCriticalSection` nesne.

```
CCriticalSection();
```

### <a name="remarks"></a>Açıklamalar

Erişim veya yayın için bir `CCriticalSection` nesne, oluşturun bir [CSingleLock](../../mfc/reference/csinglelock-class.md) nesne ve çağrı kendi [kilit](../../mfc/reference/csinglelock-class.md#lock) ve [kilidini](../../mfc/reference/csinglelock-class.md#unlock) üye işlevleri. Varsa `CCriticalSection` nesne kullanılan tek başına, çağrı kendi [kilidini](#unlock) bunu serbest bırakmak için üye işlevi.

Oluşturucu bir yetersiz bellek özel gerekli sistem bellek ayırma başarısız olursa (tür [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) otomatik olarak oluşturulur.

### <a name="example"></a>Örnek

  Örneğin bakın [CCriticalSection::Lock](#lock).

##  <a name="lock"></a>  CCriticalSection::Lock

Kritik bölüm nesneye erişmek için bu üye işlevini çağırın.

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>Parametreler

*dwTimeout*<br/>
`Lock` Bu parametreyi yok sayar.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`Lock` kritik bölüm nesnesi sinyal kadar döndürmez engelleyici bir çağrıdır (kullanılabilir olur).

Zamanlanmış bekler gerekliyse, kullanabileceğiniz bir [CMutex](../../mfc/reference/cmutex-class.md) yerine Nesne bir `CCriticalSection` nesne.

Varsa `Lock` gerekli sistem bellek, bellek özel durumu başarısız (tür [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) otomatik olarak oluşturulur.

### <a name="example"></a>Örnek

Bu örnek, paylaşılan bir kaynağa erişimi denetleyerek iç içe geçmiş kritik bölüm yaklaşımı gösterir (statik `_strShared` nesnesi) paylaşılan kullanarak `CCriticalSection` nesne. `SomeMethod` İşlevi gösterir güvenli bir şekilde paylaşılan bir kaynağa güncelleştiriliyor.

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

##  <a name="m_sect"></a>  CCriticalSection::m_sect

Tüm tarafından kullanılan kritik bölüm nesnesi içeren `CCriticalSection` yöntemleri.

```
CRITICAL_SECTION m_sect;
```

##  <a name="operator_critical_section_star"></a>  CCriticalSection::operator CRITICAL_SECTION *

CRITICAL_SECTION nesnesi alır.

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>Açıklamalar

İç CRITICAL_SECTION nesnenin işaretçisini almak için bu işlevi çağırın.

##  <a name="unlock"></a>  CCriticalSection::Unlock

Yayınları `CCriticalSection` başka bir iş parçacığı tarafından kullanılacak nesne.

```
BOOL Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

Gösterimiyse `CCriticalSection` nesne iş parçacığı tarafından ait ve yayın başarılı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsa `CCriticalSection` tek başına kullanılan `Unlock` kritik bölümü tarafından denetlenen kaynak kullanımını tamamlandıktan hemen sonra çağrılmalıdır. Varsa bir [CSingleLock](../../mfc/reference/csinglelock-class.md) nesne kullanılıyor, `CCriticalSection::Unlock` kilit nesnenin tarafından çağrılacak `Unlock` üye işlevi.

### <a name="example"></a>Örnek

  Örneğin bakın [CCriticalSection::Lock](#lock).

## <a name="see-also"></a>Ayrıca bkz.

[CSyncObject Sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMutex Sınıfı](../../mfc/reference/cmutex-class.md)
