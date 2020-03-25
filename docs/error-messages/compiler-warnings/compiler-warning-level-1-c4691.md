---
title: Derleyici Uyarısı (düzey 1) C4691
ms.date: 11/04/2016
f1_keywords:
- C4691
helpviewer_keywords:
- C4691
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
ms.openlocfilehash: 8065129e20b627eb387421455527f6aaec3fdc2f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175382"
---
# <a name="compiler-warning-level-1-c4691"></a>Derleyici Uyarısı (düzey 1) C4691

' Type ': başvurulan tür, başvurulmayan ' File ' derlemesinde bekleniyordu, bunun yerine geçerli çeviri biriminde tanımlanan tür kullanıldı

Özgün tür tanımını içeren meta veri dosyasına başvurulmuyor ve derleyici yerel bir tür tanımı kullanıyor.

*Dosyayı*yeniden oluşturduğunuz durumda, C4691, pragma [Warning](../../preprocessor/warning.md)ile yoksayılabilir veya kapatılabilir.  Diğer bir deyişle, oluşturmakta olduğunuz dosya derleyicinin tür tanımını bulmayı beklediği dosyayla aynıysa, C4691 'yi yoksayabilirsiniz.

Ancak, derleyici meta verilerde başvurulan derlemeden aynı derlemeden olmayan bir tanım kullanıyorsa beklenmeyen bir davranış meydana gelebilir; CLR türleri yalnızca türün adı ile değil, derleme tarafından da yazılır.  Diğer bir deyişle, z. dll derlemesinden z türü, y. dll ' den Z 'den farklı.

## <a name="example"></a>Örnek

Bu örnek, özgün tür tanımını içerir.

```cpp
// C4691_a.cpp
// compile with: /clr /LD /W1
public ref class Original_Type {};
```

## <a name="example"></a>Örnek

Bu örnek C4691_a. dll ' ye başvurur ve Original_Type türünde bir alan bildirir.

```cpp
// C4691_b.cpp
// compile with: /clr /LD
#using "C4691_a.dll"
public ref class Client {
public:
   Original_Type^ ot;
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C4691 oluşturur.  Bu örnekte Original_Type için bir tanım ve C4691a. dll ' nin başvurmadığından dikkat edin.

Çözümlemek için, özgün tür tanımını içeren meta veri dosyasına başvurun ve yerel bildirimi ve tanımı kaldırın.

```cpp
// C4691_c.cpp
// compile with: /clr /LD /W1
// C4691 expected

// Uncomment the following line to resolve.
// #using "C4691_a.dll"
#using "C4691_b.dll"

// Delete the following line to resolve.
ref class Original_Type;

public ref class MyClass : Client {};
```
