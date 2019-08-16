---
title: CComEnum sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
ms.openlocfilehash: 7252eb2fa5d34618a1c38484a2506bae27a1106a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497218"
---
# <a name="ccomenum-class"></a>CComEnum sınıfı

Bu sınıf bir diziyi temel alan bir COM Numaralandırıcı nesnesi tanımlar.

## <a name="syntax"></a>Sözdizimi

```
template <class Base,
    const IID* piid, class T, class Copy, class ThreadModel = CcomObjectThreadModel>
class ATL_NO_VTABLE CComEnum : public CComEnumImpl<Base, piid,
T,
    Copy>,
public CComObjectRootEx<ThreadModel>
```

#### <a name="parameters"></a>Parametreler

*Temel*<br/>
COM Numaralandırıcı arabirimi. Örnek için bkz. [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) .

*piıd*<br/>
Numaralandırıcı arabiriminin arabirim KIMLIĞINE yönelik bir işaretçi.

*ŞI*<br/>
Numaralandırıcı arabirimi tarafından kullanıma sunulan öğenin türü.

*Kopyala*<br/>
Homojen [kopya ilke sınıfı](../../atl/atl-copy-policy-classes.md).

*ThreadModel*<br/>
Sınıfın iş parçacığı modeli. Bu parametrenin varsayılan değeri, projenizde kullanılan genel nesne iş parçacığı modelidir.

## <a name="remarks"></a>Açıklamalar

`CComEnum`bir diziyi temel alan bir COM Numaralandırıcı nesnesi tanımlar. Bu sınıf, C++ standart bir kitaplık kapsayıcısını temel alan bir Numaralandırıcı uygulayan [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) öğesine benzerdir. Bu sınıfı kullanmanın tipik adımları aşağıda özetlenmiştir. Daha fazla bilgi için bkz. [atl koleksiyonları ve Numaralandırıcılar](../../atl/atl-collections-and-enumerators.md).

## <a name="to-use-this-class"></a>Bu sınıfı kullanmak için:

- **typedef** bu sınıfın özelleştirmesi.

- Öğesinin`CComObject`bir özelleştirmesi içinde şablon bağımsız değişkeni olarak **typedef** kullanın.

- `CComObject` Özelleşmenin bir örneğini oluşturun.

- [CComEnumImpl:: Init](../../atl/reference/ccomenumimpl-class.md#init)çağırarak Numaralandırıcı nesnesini başlatın.

- Numaralandırıcı arabirimini istemciye döndürün.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CComObjectRootBase`

`Base`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

[CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)

`CComEnum`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="example"></a>Örnek

Aşağıda gösterilen kod, bir Numaralandırıcı nesnesi oluşturmak ve başlatmak için yeniden kullanılabilir bir işlev sağlar.

[!code-cpp[NVC_ATL_COM#32](../../atl/codesnippet/cpp/ccomenum-class_1.h)]

Bu şablon işlevi, `_NewEnum` aşağıda gösterildiği gibi bir koleksiyon arabiriminin özelliğini uygulamak için kullanılabilir:

[!code-cpp[NVC_ATL_COM#33](../../atl/codesnippet/cpp/ccomenum-class_2.h)]

Bu kod, bir için `CComEnum` bir typedef oluşturur ve bu, `IEnumVariant` arabirim aracılığıyla bir çeşit vektörü gösterir. `CVariantArrayCollection` Sınıfı`CreateEnumerator` , bu türün Numaralandırıcı nesneleriyle çalışmayı özelleştirmektedir ve gerekli bağımsız değişkenleri geçirir.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)<br/>
[CComEnumImpl Sınıfı](../../atl/reference/ccomenumimpl-class.md)<br/>
[CComObjectRootEx Sınıfı](../../atl/reference/ccomobjectrootex-class.md)
