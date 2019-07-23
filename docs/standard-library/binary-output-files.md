---
title: İkili Çıktı Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
ms.openlocfilehash: 4562f5c1167aeadc6689313e73545ed1ad9bbcf8
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376336"
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

Bu programın {99, 0, 10, 0}; bayt dizisinin çıktısını almak için bekliyor olabilirsiniz Bunun yerine, ikili girişi bekleyen bir program için sorunlara neden olan {99, 0, 13, 10, 0} çıkışı verir. Doğru ikili çıktıya ihtiyacınız varsa, bu karakterlerin çevrilmeden yazıldığı, [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) Oluşturucu `openmode` bağımsız değişkenini kullanarak ikili çıkış belirtebilirsiniz:

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

[Çıkış Akışları](../standard-library/output-streams.md)
