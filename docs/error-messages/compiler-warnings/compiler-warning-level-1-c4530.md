---
title: Derleyici Uyarısı (düzey 1) C4530
description: Microsoft C++ derleyicisi uyarı C4530 'e yönelik başvuru kılavuzu.
ms.date: 04/02/2020
f1_keywords:
- C4530
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
ms.openlocfilehash: fe0a2b4c8eb881327f3e59d66e7e6941f0a2cad8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230668"
---
# <a name="compiler-warning-level-1-c4530"></a>Derleyici Uyarısı (düzey 1) C4530

> C++ özel durum işleyicisi kullanıldı, ancak geriye doğru izleme semantiği etkin değil. /EHsc belirtin

Kod C++ özel durum işlemeyi kullanır, ancak bu derleyici seçeneklerinde [/EHsc](../../build/reference/eh-exception-handling-model.md) dahil edilmedi.

## <a name="remarks"></a>Açıklamalar

Derleyici, **`/EHsc`** özel durum işleme Için c++ standardını Izleyen c++ kodu oluşturma seçeneğini gerektirir. Standart C++ *geriye doğru izleme semantiği* , bir özel durumun oluşturulduğu ve nerede yakalandığı ve kaynakları kurtarıldığı durumlar arasında oluşturulan nesneler ve yığın çerçevelerini belirtir. Bu işlem *yığının geri sarımı*olarak bilinir.

**`/EHsc`** Seçeneği, bir özel durum içeren yığın çerçevesi aracılığıyla geçtiğinde derleyiciye otomatik depolama nesnelerinde yıkıcıları çağıran kod oluşturmasını söyler. *Otomatik depolama* nesneleri, yerel değişkenler gibi yığında ayrılan nesnelerdir. Otomatik depolama denir çünkü işlevler çağrıldığında otomatik olarak ayrılır ve geri döntiklerinde otomatik olarak serbest bırakılır. Yığın çerçevesi, bir işlev çağrıldığında, otomatik depolama alanı ile birlikte yığına yerleştirilmiş olan verilerden oluşan bir *çerçevedir* .

Bir özel durum oluştuğunda, yakalanmadan önce çeşitli yığın çerçevelerinden geçebiliriz. Bu yığın çerçeveleri, ters arama sırasıyla bunlar arasında geçiş yaparken, bu yığın çerçevelerinin kaldırılması gerekir. Her yığın çerçevesindeki otomatik depolama nesneleri, kaynaklarını düzgün bir şekilde kurtarmak için yok edilmelidir. Bu, bir işlev normal olarak döndürüldüğünde otomatik olarak gerçekleşen yok etme ve kurtarma işlemidir.

**`/EHsc`** Seçenek etkin olmadığında, yığın çerçevelerinde oluşturma işlevi ve özel durumun yakalandığı işlev arasındaki otomatik depolama nesneleri yok etme yok edilir. Yalnızca bir veya bloğunda oluşturulan otomatik depolama nesneleri **`try`** **`catch`** , önemli kaynak sızıntılarına ve diğer beklenmeyen davranışlara neden olabilecek şekilde yok edilir.

Yürütülebilir dosyada büyük olasılıkla bir özel durum oluşturulamazsa, bu uyarıyı güvenle yoksayabilirsiniz. Bazı kodlar, başka özel durum işleme seçenekleri gerektirebilir. Daha fazla bilgi için bkz. [/Eh](../../build/reference/eh-exception-handling-model.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4530 oluşturur:

```cpp
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

**`/EHsc`** Uyarıyı çözmek için ile örneği derleyin.
