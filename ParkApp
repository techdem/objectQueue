import javax.swing.*;
import java.util.*;

public class ParkApp {

    public static void main (String[] args) {

        JFrame selection = new JFrame();
        int userChoice = 0;
        int returnMenu;
        boolean valid = false;
        String[] adultOrChildOption = new String[2];
        adultOrChildOption[0] = "Adult";
        adultOrChildOption[1] = "Child";
        int adultOrChild;
        ArrayList<Booking> bookings = new ArrayList<Booking>();
        int index = -1;

        do {

            while (!valid) {

                try {
                    userChoice = Integer.parseInt(JOptionPane.showInputDialog(null,
                            "Welcome to the Universal Orlando Theme Park Bookings App!\n" +
                                    "(by Tudor Chiribes)\n\n" +
                                    "Please select one of the following options:\n" +
                                    "(by typing the corresponding number in the box)\n\n" +
                                    "1. Bookings for adult and child\n" +
                                    "2. View next adult booking\n" +
                                    "3. View next child booking\n" +
                                    "4. View total amount of bookings\n" +
                                    "5. Check if there are any bookings\n" +
                                    "6. Exit the application."));

                    if (userChoice > 0 && userChoice < 7) {

                        valid = true;
                    }
                    else {

                        JOptionPane.showMessageDialog(null,
                                "Please type a number that matches one of the options.");
                    }

                } catch (Exception badInput) {

                    JOptionPane.showMessageDialog(null,
                            "Please type a number that matches one of the options.");
                }
            }

            switch (userChoice) {

                case 1:

                    adultOrChild=JOptionPane.showOptionDialog(selection.getContentPane(),
                            "Do you wish to create a booking for an adult or a child?",
                            "Type of booking:",0,
                            JOptionPane.INFORMATION_MESSAGE,null,adultOrChildOption,null);

                        String name = JOptionPane.showInputDialog(null,
                                "Please type the name:\n");
                        String time = JOptionPane.showInputDialog(null,
                                "Please type the time:\n");

                        bookings.add(new Booking(adultOrChild, name, time));
                    break;

                case 2:

                    for (int i = 0; i < bookings.size(); i++) {

                        if (bookings.get(i).getBookingType() == 0) {

                            index = i;
                            break;
                        }
                    }

                    if (index != -1) {

                        JOptionPane.showMessageDialog(null,
                                "Next adult booking is:\n\n" +
                                        bookings.get(index));

                        bookings.remove(index);
                    }
                    else {

                        JOptionPane.showMessageDialog(null,
                                "There is currently no adult booking...");
                    }
                    break;

                case 3:

                    for (int i = 0; i < bookings.size(); i++) {

                        if (bookings.get(i).getBookingType() == 1) {

                            index = i;
                            break;
                        }
                    }

                    if (index != -1) {

                        JOptionPane.showMessageDialog(null,
                                "Next child booking is:\n\n" +
                                        bookings.get(index));
                        bookings.remove(index);
                    }
                    else {

                        JOptionPane.showMessageDialog(null,
                                "There is currently no child booking...");
                    }
                    break;

                case 4:

                    JOptionPane.showMessageDialog(null,
                            bookings.size());
                    break;

                case 5:

                    if (!bookings.isEmpty()) {

                        JOptionPane.showMessageDialog(null,
                                "Yes, there are bookings!");
                    }
                    else {

                        JOptionPane.showMessageDialog(null,
                                "No, there are no bookings.");
                    }
                    break;

                case 6:

                    break;

                default:

                    System.out.println("Option not valid, please check validation logic...");
            }

            returnMenu = JOptionPane.showConfirmDialog(null,
                    "Would you like to choose another option?");
            valid = false;
            index = -1;

        } while (returnMenu == JOptionPane.YES_OPTION);

        JOptionPane.showMessageDialog(null,"Thank you for using the app!");
    }
}
