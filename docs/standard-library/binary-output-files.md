---
title: İkili Çıktı Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
ms.openlocfilehash: 99445275a8f92622f451e8a88082dc2b28fb60b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615652"
---
# <a name="binary-output-files"></a>İkili Çıktı Dosyaları

Varsayılan çıkış modu, metin, bu nedenle akışları başlangıçta metni için tasarlanmıştır. Metin modunda bir satır başı return-satır besleme için (yalnızca 16-bit) yeni satır karakteri (onaltılık 10) genişletir. Genişletme, burada gösterildiği gibi sorunlara neden olabilir:

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

Bu program çıkış bayt dizisi {99, 0, 10, 0}; bekleyebilirsiniz. Bunun yerine, onu {99, 0, 13, 10, 0}, ikili giriş bekleniyor bir program için sorunlara neden olan çıkarır. Çevrilmeden karakter yazılır ikili çıktıyı true varsa kullanarak ikili çıktıyı belirtebilirsiniz [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) Oluşturucu AçmaModu bağımsız değişkeni:

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

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
