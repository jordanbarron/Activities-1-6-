package jordan.dev.com.flickr_viewer;

import android.support.v7.app.ActionBarActivity;
import android.os.Bundle;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ArrayAdapter;
import android.widget.ImageView;
import android.widget.ListView;
import android.widget.TextView;

import java.util.ArrayList;
import java.util.List;


public class ActivityLocation extends ActionBarActivity {

    private ListView listLocations;
    private List<String> cities;
    private List<String> countries;
    private List<Integer> flags;





    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_activity_location);

        listLocations = (ListView)findViewById(R.id.listLocations);

        cities = new ArrayList<String>();
        countries = new ArrayList<>();
        flags = new ArrayList<>();





        cities.add("Hong Kong");
        countries.add("China");
        flags.add(R.drawable.china);
        cities.add("London");
        countries.add("England");
        flags.add(R.drawable.united_kingdom);
        cities.add("Bridgetown");
        countries.add("Barbados");
        flags.add(R.drawable.barbados);
        cities.add("Belgium");
        countries.add("Brussels");
        flags.add(R.drawable.belgium);
        cities.add("Sydney");
        countries.add("Australia");
        flags.add(R.drawable.australia);
        cities.add("Sao Paulo");
        countries.add("Brazil");
        flags.add(R.drawable.brazil);
        cities.add("Havana");
        countries.add("Cuba");
        flags.add(R.drawable.cuba);
        cities.add("Kingston");
        countries.add("Jamaica");
        flags.add(R.drawable.jamaica);
        cities.add("Tokyo");
        countries.add("Japan");
        flags.add(R.drawable.japan);
        cities.add("Riga");
        countries.add("Latvia");
        flags.add(R.drawable.latvia);

        LocationAdapter adapter = new LocationAdapter(cities);


        listLocations.setAdapter(adapter);


    }


    private class LocationAdapter extends ArrayAdapter<String> {

        public LocationAdapter(List<String> items) {
            super(ActivityLocation.this, 0, items);
        }

        @Override
        public View getView(int position, View convertView, ViewGroup parent) {

            if (convertView == null) {
                convertView = getLayoutInflater().inflate(
                        R.layout.layout, null);
            }

            TextView lblCityName = (TextView)convertView.findViewById(R.id.lblCityName);
            TextView lblCountry = (TextView)convertView.findViewById(R.id.lblCountry);
            ImageView imgflags = (ImageView)convertView.findViewById(R.id.imgFlag);


            lblCityName.setText(cities.get(position));
            lblCountry.setText(countries.get(position));
            imgflags.setImageResource(flags.get(position));



            return convertView;
        }// end get view

    }// end adapter class


}

