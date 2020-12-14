---
description: 'Daha fazla bilgi edinin: Ckritiksection sınıfı'
title: Ckritiksection sınıfı
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
ms.openlocfilehash: 0041eea4453ec02159b26805bd5e7a264a410504
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227799"
---
# <a name="ccriticalsection-class"></a>Ckritiksection sınıfı

Bir kaynağa veya kod bölümüne erişmek için bir seferde bir iş parçacığına izin veren bir eşitleme nesnesi olan bir "kritik bölümü" temsil eder.

## <a name="syntax"></a>Syntax

```
class CCriticalSection : public CSyncObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Ckritiksection:: Ccriticalhandle bölümü](#ccriticalsection)|Bir `CCriticalSection` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Ckritiksection:: Lock](#lock)|Nesnesine erişim kazanmak için kullanın `CCriticalSection` .|
|[Ckritiksection:: unlock](#unlock)|Nesneyi serbest bırakır `CCriticalSection` .|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Ccriticalhandle bölümü:: operator CRITICAL_SECTION *](#operator_critical_section_star)|İç CRITICAL_SECTION nesnesine bir işaretçi alır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Ckritiksection:: m_sect](#m_sect)|CRITICAL_SECTION nesnesi.|

## <a name="remarks"></a>Açıklamalar

Kritik bölümler, tek seferde yalnızca bir iş parçacığının verileri veya diğer denetlenen kaynakları değiştirmesine izin verildiğinde faydalıdır. Örneğin, bağlantılı bir listeye düğüm eklemek, tek seferde yalnızca bir iş parçacığı tarafından izin verilmesi gereken bir işlemdir. `CCriticalSection`Bağlantılı listeyi denetlemek için bir nesne kullanarak, aynı anda yalnızca bir iş parçacığı listeye erişim sağlayabilir.

> [!NOTE]
> Sınıfının işlevselliği, `CCriticalSection` gerçek bir Win32 CRITICAL_SECTION nesnesi tarafından sağlanır.

Kritik bölümler, hız önemli olduğunda ve kaynak işlem sınırları boyunca kullanılmayacak zaman uyumu (bkz. [CMutex](../../mfc/reference/cmutex-class.md)) yerine kullanılır.

Bir nesne kullanmanın iki yöntemi vardır `CCriticalSection` : tek başına ve bir sınıfa eklenmiş.

- Tek başına yöntemi tek başına bir nesne kullanmak Için `CCriticalSection` , `CCriticalSection` gerektiğinde nesnesini oluşturun. Oluşturucudan başarılı bir geri dönmeden sonra, nesneyi bir [kilit](#lock)çağrısıyla açıkça kilitleyin. Kritik bölüme erişirken [kilit açma](#unlock) çağrısı yapın. Bu yöntem, kaynak kodunuzu okuyan bir kişiye daha açık olsa da daha fazla hataya yol açabilir.

   Daha tercih edilen bir yöntem [CSingleLock](../../mfc/reference/csinglelock-class.md) sınıfını kullanmaktır. Ayrıca bir `Lock` ve yöntemi vardır `Unlock` , ancak bir özel durum oluşursa kaynağın kilidini açmak için endişelenmeniz gerekmez.

- Gömülü Yöntem ayrıca, `CCriticalSection` sınıfa bir-Type veri üyesi ekleyerek ve gerektiğinde veri üyesini kilitleyerek birden çok iş parçacığı içeren bir sınıfı paylaşabilirsiniz.

Nesneleri kullanma hakkında daha fazla bilgi için `CCriticalSection` bkz. [Çoklu iş parçacığı kullanımı: eşitleme sınıflarını kullanma](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CSyncObject](../../mfc/reference/csyncobject-class.md)

`CCriticalSection`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxmt. h

## <a name="ccriticalsectionccriticalsection"></a><a name="ccriticalsection"></a> Ckritiksection:: Ccriticalhandle bölümü

Bir `CCriticalSection` nesnesi oluşturur.

```
CCriticalSection();
```

### <a name="remarks"></a>Açıklamalar

Bir nesneye erişmek veya onu serbest bırakmak için `CCriticalSection` bir [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi oluşturun ve [Lock](../../mfc/reference/csinglelock-class.md#lock) ve [unlock](../../mfc/reference/csinglelock-class.md#unlock) üye işlevlerini çağırın. `CCriticalSection`Nesne tek başına kullanılıyorsa, serbest bırakmak için üye [kilit](#unlock) işlevini çağırın.

Oluşturucu gerekli sistem belleğini ayıramazsa, bir bellek özel durumu ( [CMemoryException](../../mfc/reference/cmemoryexception-class.md)türünde) otomatik olarak oluşturulur.

### <a name="example"></a>Örnek

  [Ckritiksection:: Lock](#lock)örneğine bakın.

## <a name="ccriticalsectionlock"></a><a name="lock"></a> Ckritiksection:: Lock

Kritik bölüm nesnesine erişim kazanmak için bu üye işlevi çağırın.

```
BOOL Lock();
BOOL Lock(DWORD dwTimeout);
```

### <a name="parameters"></a>Parametreler

*dwTimeout*<br/>
`Lock` Bu parametre değerini yoksayar.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`Lock` , kritik bölüm nesnesi sinyallene (kullanılabilir olur) kadar geri dönemeyecek bir engelleme çağrıdır.

Süresi dolmuşsa, bir nesnesi yerine bir [CMutex](../../mfc/reference/cmutex-class.md) nesnesi kullanabilirsiniz `CCriticalSection` .

`Lock`Gerekli sistem belleğini ayıramazsa, bir bellek özel durumu ( [CMemoryException](../../mfc/reference/cmemoryexception-class.md)türünde) otomatik olarak oluşturulur.

### <a name="example"></a>Örnek

Bu örnekte paylaşılan bir nesne kullanarak paylaşılan bir kaynağa (statik nesne) erişimi denetleyerek iç içe geçmiş kritik bölüm yaklaşımı gösterilmektedir `_strShared` `CCriticalSection` . `SomeMethod`İşlevi, paylaşılan bir kaynağın güvenli bir şekilde güncelleştirilmesini gösterir.

[!code-cpp[NVC_MFC_Utilities#11](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]

## <a name="ccriticalsectionm_sect"></a><a name="m_sect"></a> Ckritiksection:: m_sect

Tüm yöntemler tarafından kullanılan kritik bir bölüm nesnesi içerir `CCriticalSection` .

```
CRITICAL_SECTION m_sect;
```

## <a name="ccriticalsectionoperator-critical_section"></a><a name="operator_critical_section_star"></a> Ccriticalhandle bölümü:: operator CRITICAL_SECTION *

Bir CRITICAL_SECTION nesnesi alır.

```
operator CRITICAL_SECTION*();
```

### <a name="remarks"></a>Açıklamalar

İç CRITICAL_SECTION nesnesine bir işaretçi almak için bu işlevi çağırın.

## <a name="ccriticalsectionunlock"></a><a name="unlock"></a> Ckritiksection:: unlock

`CCriticalSection`Nesneyi başka bir iş parçacığı tarafından kullanılmak üzere serbest bırakır.

```
BOOL Unlock();
```

### <a name="return-value"></a>Dönüş Değeri

`CCriticalSection`Nesnenin iş parçacığına ait olması ve yayın başarılı olması durumunda sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CCriticalSection`Tek başına kullanılıyorsa, `Unlock` kritik bölüm tarafından denetlenen kaynağın kullanımını tamamladıktan hemen sonra çağrılmalıdır. Bir [CSingleLock](../../mfc/reference/csinglelock-class.md) nesnesi kullanılıyorsa, `CCriticalSection::Unlock` kilit nesnesinin `Unlock` üye işlevi tarafından çağırılır.

### <a name="example"></a>Örnek

  [Ckritiksection:: Lock](#lock)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CSyncObject sınıfı](../../mfc/reference/csyncobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMutex sınıfı](../../mfc/reference/cmutex-class.md)
