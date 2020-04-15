---
title: Derleyici Uyarısı (düzey 1) C4530
description: Microsoft C++ derleyici uyarı C4530 başvuru kılavuzu.
ms.date: 04/02/2020
f1_keywords:
- C4530
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
ms.openlocfilehash: 9de88a4b0b6c7176ff82b68c92d09d9fe75a70b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369778"
---
# <a name="compiler-warning-level-1-c4530"></a>Derleyici Uyarısı (düzey 1) C4530

> C++ özel durum işleyicisi kullanılır, ancak gevşeme semantik etkin değildir. Belirt /EHsc

Kod C++ özel durum işleme kullanır, ancak [/EHsc](../../build/reference/eh-exception-handling-model.md) derleyici seçeneklerine dahil edilmedi.

## <a name="remarks"></a>Açıklamalar

Derleyici, özel **`/EHsc`** durum işleme için C++ standardını izleyen C++ kodu oluşturma seçeneğini gerektirir. Standart C++ *gevşeme semantik,* bir özel durum atıldığı ve yakalandığı yerler arasında inşa edilen nesnelerin ve yığın çerçevelerinin yok edilmesi ve kaynaklarının kurtarılması gerektiğini belirtir. Bu işlem *yığını gevşetme*olarak bilinir.

Seçenek, **`/EHsc`** derleyiciye, bir özel durum içeren yığın çerçevesinden geçtiğinde otomatik depolama nesnelerinde yıkıcıları çağıran kod oluşturmasını söyler. *Otomatik depolama* nesneleri, yerel değişkenler gibi yığına ayrılan nesnelerdir. Otomatik depolama olarak adlandırılır, çünkü işlevler çağrıldığında otomatik olarak tahsis edilir ve döndüklerinde otomatik olarak serbest bırakılır. *Yığın çerçevesi,* bir işlev çağrıldığında yığına yerleştirilen verilerdir.

Bir özel durum atıldığında, yakalanmadan önce birkaç yığın karesi arasında seyahat edebilir. Bu yığın çerçeveleri, özel durum ters arama sırasına göre içinden geçerken çözülmelidir. Her yığın çerçevesindeki otomatik depolama nesneleri, kaynaklarını temiz bir şekilde kurtarmak için yok edilmelidir. Bir işlev normal döndüğünde otomatik olarak gerçekleşen aynı yıkım ve kurtarma işlemidir.

**`/EHsc`** Seçenek etkinleştirilemediği zaman, atma işlevi ile özel durum yakalanan işlev arasındaki yığın çerçevelerinde otomatik depolama nesneleri yok olmaz. Yalnızca **deneme** veya **yakalama** bloğunda oluşturulan otomatik depolama nesneleri yok edilir ve bu da önemli kaynak sızıntılarına ve diğer beklenmeyen davranışlara yol açabilir.

Yürütülebilir cihazınıza herhangi bir özel durum atılamazsa, bu uyarıyı güvenle yok sayabilirsiniz. Bazı kodlar diğer özel durum işleme seçenekleri gerektirebilir. Daha fazla bilgi için bkz: [/EH](../../build/reference/eh-exception-handling-model.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4530 üretir:

```cpp
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

Uyarıyı çözmek **`/EHsc`** için örneği derle.
