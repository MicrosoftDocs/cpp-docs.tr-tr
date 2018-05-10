---
title: İkili çıktı dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdb101620b1a61f3a29057ee408cf9e89d38f9e8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="binary-output-files"></a>İkili Çıktı Dosyaları

Varsayılan çıkış modu metindir şekilde akışları başlangıçta metin için tasarlanmıştır. Metin modunda yeni satır karakteri (onaltılık 10) bir satır başı-satır besleme için (yalnızca 16 bit) genişletir. Genişletme, aşağıda gösterildiği gibi sorunlara neden olabilir:

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

{99, 0, 10, 0}; bayt dizisi çıkarmak için bu programı bekleyebilirsiniz Bunun yerine, onu {99, 0, 13, 10, 0}, ikili girişi bekleniyor bir program için sorunlara neden olan çıkarır. Untranslated karakter yazılır ikili çıktıyı true varsa, kullanarak ikili çıktıyı belirtebilirsiniz [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) Oluşturucu AçmaModu bağımsız değişkeni:

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
