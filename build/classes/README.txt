Source v1 : https://www.youtube.com/watch?v=vTIHHsRYEA8

 try {
            int bcode = parseInt(txtbcode.getText());
            String bname = txtbname.getText();
            int price = parseInt(txtprice.getText());
            int qty = (Integer)txtqty.getValue();
            int tcost = parseInt(txttcost.getText());
            int pay= parseInt(txtpay.getText());
            int balance = parseInt(txtbal.getText());

            pst = con.prepareStatement("INSERT INTO sales_product (bcode,bname,price,qty,tcost,pay,balance)VALUES(?,?,?,?,?,?,?)");
            pst.setInt(1,bcode);
            pst.setString(2,bname);
            pst.setInt(3, price);
            pst.setInt(4, (qty));
            pst.setInt(5,tcost);
            pst.setInt(6, pay);
            pst.setInt(7,balance);

            int k = pst.executeUpdate();

            if(k==1) {
                JOptionPane.showMessageDialog(this,
                        "Record Added!! successfully!",
                        "Message",
                        JOptionPane.INFORMATION_MESSAGE);
                txtbcode.setText("");
                txtbname.setText("");
                txtprice.setText("");
                txtqty.setValue(1);
                txttcost.setText("");
                txtpay.setText("");
                txtbal.setText("");
            }else{
                JOptionPane.showMessageDialog(this,"Record failed to saved!!!");
            }

        } catch (SQLException ex) {
            Logger.getLogger(BookShop.class.getName()).log(Level.SEVERE, null, ex);
        }