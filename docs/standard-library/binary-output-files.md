---
description: 'Daha fazla bilgi edinin: Ikili çıktı dosyaları'
title: İkili Çıktı Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
ms.openlocfilehash: acbefe8eb7f091bf3d323f25ff00464068d9b1f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325524"
---
# <a name="binary-output-files"></a>İkili Çıktı Dosyaları

Akışlar başlangıçta metin için tasarlanmıştı, bu nedenle varsayılan çıktı modu metindir. Metin modunda, satır besleme (yeni satır) karakteri bir satır başı satır akışı çiftine genişletilir. Genişletme, burada gösterildiği gibi sorunlara neden olabilir:

```cpp
// binary_output_files.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };
int main( )
{
    ofstream os( "test.dat" );
    os.write( (char *) iarray, sizeof( iarray ) );
}
```

Bu programın {99, 0, 10, 0}; bayt dizisinin çıktısını almak için bekliyor olabilirsiniz Bunun yerine, ikili girişi bekleyen bir program için sorunlara neden olan {99, 0, 13, 10, 0} çıkışı verir. Doğru ikili çıktıya ihtiyacınız varsa, bu karakterlerin çevrilmeden yazıldığı, [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) Oluşturucu bağımsız değişkenini kullanarak ikili çıkış belirtebilirsiniz `openmode` :

```cpp
// binary_output_files2.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };

int main()
{
   ofstream ofs ( "test.dat", ios_base::binary );

   // Exactly 8 bytes written
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış akışları](../standard-library/output-streams.md)
