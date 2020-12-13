---
description: 'Hakkında daha fazla bilgi edinin: __ud2'
title: __ud2
ms.date: 09/02/2019
f1_keywords:
- __ud2
helpviewer_keywords:
- UD2 instruction
- __ud2 intrinsic
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
ms.openlocfilehash: 2b5f0b9ffec066baa3eb2fa212dfc7baf3a6cb49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333666"
---
# <a name="__ud2"></a>__ud2

**Microsoft'a Özgü**

Tanımsız bir yönerge üretir.

## <a name="syntax"></a>Syntax

```C
void __ud2();
```

## <a name="remarks"></a>Açıklamalar

Tanımlanmamış bir yönerge çalıştırırsanız, işlemci geçersiz bir Opcode özel durumu oluşturur.

`__ud2`İşlevi `UD2` makine yönergesine eşdeğerdir ve yalnızca çekirdek modunda kullanılabilir. Daha fazla bilgi için, [Intel Corporation](https://software.intel.com/articles/intel-sdm) sitesinde "Intel mimarisi yazılım geliştiricisi el kitabı, toplu 2: yönerge kümesi başvurusu" belgesinde arama yapın.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__ud2`|x86, x64|

**Üst bilgi dosyası**\<intrin.h>

**SON Microsoft 'a özgü**

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir özel durum harekete geçiren tanımsız bir yönerge yürütür. Ardından, özel durum işleyicisi, dönüş kodunu sıfırdan bir olarak değiştirir.

```cpp
// __ud2_intrinsic.cpp
#include <stdio.h>
#include <intrin.h>
#include <excpt.h>
// compile with /EHa

int main() {

// Initialize the return code to 0.
int ret = 0;

// Attempt to execute an undefined instruction.
  printf("Before __ud2(). Return code = %d.\n", ret);
  __try {
  __ud2();
  }

// Catch any exceptions and set the return code to 1.
  __except(EXCEPTION_EXECUTE_HANDLER){
  printf("  In the exception handler.\n");
  ret = 1;
  }

// Report the value of the return code.
  printf("After __ud2().  Return code = %d.\n", ret);
  return ret;
}
```

```Output
Before __ud2(). Return code = 0.
  In the exception handler.
After __ud2().  Return code = 1.
```

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
