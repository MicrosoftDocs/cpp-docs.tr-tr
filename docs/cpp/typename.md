---
title: typename
ms.date: 11/04/2016
f1_keywords:
- typename_cpp
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
ms.openlocfilehash: 789bb879922bbd96a04085159205d02fb7f495c8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160690"
---
# <a name="typename"></a>typename

Şablon tanımlarında, derleyiciye bilinmeyen bir tanımlayıcının bir tür olduğunu belirten bir ipucu sağlar. Şablon parametresi listelerinde, bir tür parametresi belirtmek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```
typename identifier;
```

## <a name="remarks"></a>Açıklamalar

Şablon tanımındaki bir ad, şablon bağımsız değişkenine bağımlı nitelikli bir ad ise bu anahtar sözcük kullanılmalıdır; nitelikli ad bağımlı değilse, bu isteğe bağlıdır. Daha fazla bilgi için bkz. [Şablonlar ve ad çözümlemesi](../cpp/templates-and-name-resolution.md).

**TypeName** , bir şablon bildiriminde veya tanımında herhangi bir yerdeki herhangi bir tür tarafından kullanılabilir. Şablon temel sınıfın şablon bağımsız değişkeni olarak kullanılmadığı sürece temel sınıf listesinde izin verilmez.

```cpp
template <class T>
class C1 : typename T::InnerType // Error - typename not allowed.
{};
template <class T>
class C2 : A<typename T::InnerType>  // typename OK.
{};
```

**TypeName** anahtar sözcüğü, **sınıf** yerine şablon parametresi listelerinde de kullanılabilir. Örneğin, aşağıdaki deyimler anlamsal olarak eşdeğerdir:

```cpp
template<class T1, class T2>...
template<typename T1, typename T2>...
```

## <a name="example"></a>Örnek

```cpp
// typename.cpp
template<class T> class X
{
   typename T::Y m_y;   // treat Y as a type
};

int main()
{
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Şablonlar](../cpp/templates-cpp.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
